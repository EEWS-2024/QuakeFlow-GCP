# Use Python 3.7 base image
FROM python:3.7

# Set the working directory in the container
WORKDIR /app

# Copy the dependency file
COPY requirements.txt /app

# Install Python dependencies using pip
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Copy the rest of your application code
COPY . /app

# Expose API port
EXPOSE 8005

# Set environment variable to ensure logs are not buffered
ENV PYTHONUNBUFFERED=1

# Start API server using gunicorn
ENTRYPOINT ["gunicorn", "app_plotly:server", "--reload", "-b", "0.0.0.0:8005"]
