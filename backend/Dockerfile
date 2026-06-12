FROM python:3.12-slim

WORKDIR /app

# Copy requirements first for better layer caching
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code explicitly to ensure changes are picked up
# (helps with some Docker caching behaviors)
COPY app ./app
COPY templates ./templates
COPY presets.yaml . 2>/dev/null || true
COPY requirements.txt . 2>/dev/null || true

EXPOSE 8000

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
