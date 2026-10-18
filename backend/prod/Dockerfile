FROM python:3.11-slim
WORKDIR /app
ENV PYTHONUNBUFFERED=1
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt gunicorn
COPY . .
EXPOSE 3002
CMD ["gunicorn", "--bind", "0.0.0.0:3002", "--workers", "2", "--access-logfile", "-", "--error-logfile", "-", "app:app"]
