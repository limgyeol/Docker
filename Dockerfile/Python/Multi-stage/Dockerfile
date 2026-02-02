FROM python:3.14-alpine AS builder
WORKDIR /app
COPY app.py .
RUN pip3 install --no-cache-dir flask

FROM python:3.14-alpine AS production
WORKDIR /app
RUN apk add --no-cache curl && rm -rf /root/.cache/
RUN adduser --disabled-password --gecos '' app-user
COPY --from=builder /usr/local/lib/python3.14/site-packages /usr/local/lib/python3.14/site-packages
COPY --from=builder /usr/local/bin /usr/local/bin
COPY --from=builder /app/app.py .
RUN chown -R app-user: /app
USER app-user
EXPOSE 80
CMD ["python3", "-m", "flask", "run", "--host=0.0.0.0", "--port=80"]