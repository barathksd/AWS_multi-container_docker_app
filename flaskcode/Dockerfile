
FROM python:3.8

WORKDIR /test

COPY requirements.txt /test/requirements.txt

RUN apt-get update && \
        apt-get install -y libsm6 libxext6 libxrender-dev && \
        pip install --upgrade pip

RUN pip install -r requirements.txt

RUN apt-get update

COPY . /test

EXPOSE 5000

CMD gunicorn --bind 0.0.0.0:5000 --workers 4 "simplepage:myapp()"

