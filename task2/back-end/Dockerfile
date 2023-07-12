FROM nginx:latest
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y python3
RUN apt-get install -y python3-pip

RUN pip3 install -U Flask

COPY ./api.py app/api.py

WORKDIR app

EXPOSE 5252
CMD ["python3", "api.py"]
