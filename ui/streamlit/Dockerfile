FROM python:3.7

WORKDIR /app

# Copy and install dependencies
COPY requirements.txt /app
RUN pip install -r requirements.txt

# Copy all application files
COPY . /app

# Expose API port
EXPOSE 8005

# Set environment variable for unbuffered logging
ENV PYTHONUNBUFFERED=1

# Start API server with Gunicorn
ENTRYPOINT ["gunicorn", "app_plotly:server", "--reload", "-b", "0.0.0.0:8005"]
