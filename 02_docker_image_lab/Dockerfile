FROM python:3.9-alpine AS builder

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

FROM python:3.9-alpine

WORKDIR /app

RUN addgroup -S appuser && adduser -S appuser -G appuser

COPY --from=builder /usr/local/lib/python3.9/site-packages/ /usr/local/lib/python3.9/site-packages/
COPY --from=builder /usr/local/bin/ /usr/local/bin/
COPY app.py .

RUN mkdir -p /tmp/app && chown -R appuser:appuser /app /tmp /var/tmp

ENV PORT=8000
ENV ROCKET_SIZE=Small

HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD python -c "import urllib.request; urllib.request.urlopen('http://localhost:8000/health')"

ARG LAB_LOGIN
ARG LAB_TOKEN
LABEL org.lab.login=$LAB_LOGIN \
      org.lab.token=$LAB_TOKEN

USER appuser

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "--workers", "1", "app:app"]
# CMD ["python", "app.py"]