FROM python:3.11-slim
WORKDIR /app
COPY backend/customer_service/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY backend/customer_service/app ./app
ENV UVICORN_HOST=0.0.0.0 UVICORN_PORT=8003 \
    POSTGRES_HOST=localhost POSTGRES_PORT=5432 \
    POSTGRES_DB=customers POSTGRES_USER=postgres POSTGRES_PASSWORD=postgres
EXPOSE 8003
CMD ["uvicorn","app.main:app","--host","0.0.0.0","--port","8003"]