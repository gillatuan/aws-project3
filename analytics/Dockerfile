FROM python:3.11-slim

WORKDIR /usr/src/app

COPY . .

RUN apt update -y && \
    pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5153

ENV DB_USERNAME=myuser
ENV DB_PASSWORD=mypassword
ENV DB_HOST=postgresql-service
ENV DB_PORT=5432
ENV DB_NAME=mydatabase 

CMD [ "python", "./app.py" ]
