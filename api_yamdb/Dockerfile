FROM python:3.7-slim

#Без этого не устанавливается psycopg2-binary==2.8.6 на мой пк
RUN apt-get update && apt-get -y install libpq-dev gcc

RUN mkdir /app

COPY requirements.txt /app

RUN pip3 install -r /app/requirements.txt --no-cache-dir

COPY . /app

WORKDIR /app

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]

LABEL author='plixplox@yandex.ru' version=1 broken_keyboards=1
