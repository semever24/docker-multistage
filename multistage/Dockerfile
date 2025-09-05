# Stage 1: Build stage
FROM python:3.11 AS builder
# Set working directory
WORKDIR /app
# Copy application files
COPY . .
# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Stage 2: Final runtime stage (using a lightweight image)
FROM python:3.11-slim
# Set working directory
WORKDIR /app
# Copy installed dependencies from builder stage
COPY --from=builder /usr/local/lib/python3.11/site-packages /usr/local/lib/python3.11/site-packages
COPY --from=builder /usr/local/bin /usr/local/bin
# Copy application source code
COPY app.py .
# Expose the application port
EXPOSE 5000
# Run the application
CMD ["python", "app.py"]