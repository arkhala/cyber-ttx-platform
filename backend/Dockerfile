FROM python:3.12-slim

WORKDIR /app

RUN pip install --no-cache-dir fastapi uvicorn[standard] jinja2 python-docx openai pydantic pydantic-settings pyyaml aiosqlite python-multipart

COPY requirements.txt* /app/ 2>/dev/null || true
RUN pip install --no-cache-dir -r requirements.txt 2>/dev/null || true

COPY . /app

EXPOSE 8000

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]