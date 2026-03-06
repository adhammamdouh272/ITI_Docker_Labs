FROM python:3.15.0a6-alpine3.23

COPY . /root/myproject

WORKDIR /root/myproject

RUN pip install -r requirements.txt

ENTRYPOINT ["gunicorn", "routes:app", "--bind", "0.0.0.0:5000" ]  