FROM python:3.11-slim
WORKDIR /app
COPY backend/product_service/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY backend/product_service/app ./app
ENV UVICORN_HOST=0.0.0.0 UVICORN_PORT=8001 \
    POSTGRES_HOST=localhost POSTGRES_PORT=5432 \
    POSTGRES_DB=products POSTGRES_USER=postgres POSTGRES_PASSWORD=postgres
EXPOSE 8001
CMD ["uvicorn","app.main:app","--host","0.0.0.0","--port","8001"]