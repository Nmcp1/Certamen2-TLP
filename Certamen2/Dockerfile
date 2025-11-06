FROM python:3.10-slim

RUN apt-get update
RUN apt-get install -y --no-install-recommends default-libmysqlclient-dev
RUN apt-get install -y --no-install-recommends build-essential
RUN apt-get install -y --no-install-recommends pkg-config
RUN apt-get install -y --no-install-recommends python3-dev
RUN rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY . /app
RUN pip install --no-cache-dir Django mysqlclient

EXPOSE 8000
CMD ["sh","-c","python manage.py migrate --noinput && python manage.py runserver 0.0.0.0:8000"]
