FROM python:3.7

COPY . /app

WORKDIR /app

RUN pip install -r requirements.txt && \
    mv config.prod.py config.py

ENTRYPOINT ["gunicorn", "--worker-class", "eventlet", "-w", "1", "wsgi:app", "-b", "0.0.0.0:5000"]
