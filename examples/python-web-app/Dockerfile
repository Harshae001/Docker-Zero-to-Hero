FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

# Install system dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-venv && \
    python3 -m venv venv

# Activate virtual environment and install Python dependencies
RUN /bin/bash -c "source venv/bin/activate && pip install -r requirements.txt"

# Set environment variables
ENV VIRTUAL_ENV=/app/venv
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

# Change working directory
WORKDIR /app/devops

# Command to run when the container starts
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]







