FROM python:3.11-slim

WORKDIR /app

# Install uv for faster dependency installation
RUN pip install uv

# Copy requirements first for better layer caching
COPY requirements.txt .

# Use uv to install dependencies
RUN uv pip install -r requirements.txt

# Don't copy application code - it will be mounted as a volume
# This enables hot-reloading during development

CMD ["flask", "run", "--host=0.0.0.0"]
