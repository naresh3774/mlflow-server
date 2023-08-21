# Build stage
FROM python:3.8.2-slim AS build

# Set up virtual environment
RUN python -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Installing packages from PyPi
RUN pip install --upgrade pip && pip install --no-cache-dir mlflow psycopg2-binary boto3

# Production stage
FROM python:3.8.2-slim

# Copying installed packages from build stage
COPY --from=build /opt/venv /opt/venv

# Set the virtual environment path
ENV PATH="/opt/venv/bin:$PATH"

# Defining start up command
EXPOSE 5000
ENTRYPOINT ["mlflow", "server"]
