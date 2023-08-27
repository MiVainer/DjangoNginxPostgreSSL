FROM python:3.9
WORKDIR /PetProject2
RUN apt-get update -y
RUN apt-get upgrade -y
COPY PetProject2/requirements.txt ./
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
COPY ./PetProject2 ./
CMD gunicorn -w 3 --chdir ./src proj.wsgi --bind 0.0.0.0:8000
