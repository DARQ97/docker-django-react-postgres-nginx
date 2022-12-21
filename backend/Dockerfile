FROM python:3.8.16-alpine3.17

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

#RUN apt-get update \&& 
#RUN apk add apt-get 
#RUN apk python3-dev gcc musl-dev libffi-dev netcat
#RUN apk add --update --no-cache python3 && ln -sf python3 /usr/bin/python
#RUN python3 -m ensurepip
RUN apk add postgresql-dev gcc python3-dev musl-dev
RUN pip install --upgrade pip
COPY ./requirements ./requirements
RUN pip install -r requirements/local.txt
RUN chmod +x /entrypoint.sh 

COPY . .

ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
