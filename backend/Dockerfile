# Use the official Python image as the base image
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Copy poetry.lock and pyproject.toml
COPY pyproject.toml poetry.lock* /app/

# Install Poetry
RUN pip install poetry

# Install dependencies
RUN poetry install --no-root

# Copy the rest of the application code
COPY . .

# Expose the application on port 8000
EXPOSE 8000

# Run the application
CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
