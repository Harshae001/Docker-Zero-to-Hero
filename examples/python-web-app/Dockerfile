FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install -y python3 python3-venv && \
    python3 -m venv venv && \
    /bin/bash -c "source venv/bin/activate && pip install -r requirements.txt"

WORKDIR /app/devops

CMD ["/bin/bash", "-c", "source venv/bin/activate && python manage.py runserver 0.0.0.0:8000"]






