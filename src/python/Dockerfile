FROM python:3.8-slim-buster

COPY src/python /python-service

WORKDIR /python-service
EXPOSE 5000
RUN ls -a
RUN pip3 install -r requirements.txt

COPY . .

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]

