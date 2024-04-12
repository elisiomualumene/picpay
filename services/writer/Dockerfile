FROM python:3.9-slim AS builder

WORKDIR /app

ADD requirements.txt requirements.txt

RUN pip install --no-cache-dir -r requirements.txt

# Estágio de produção
FROM python:3.9-slim

WORKDIR /app

COPY --from=builder /usr/local/lib/python3.9/site-packages/ /usr/local/lib/python3.9/site-packages/
COPY . .

EXPOSE 8081

CMD ["python", "main.py"]
