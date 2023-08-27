FROM python:3.10
# Рабочая директория внутри проекта
WORKDIR /usr/src/APP
# Переменный пайтона
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
# Устанавливаем зависимости для Postgre
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y netcat-traditional

# проверка кода через линтер
RUN pip install flake8
COPY . .
RUN flake8 --ignore=E501,F401 /usr/src/APP

# устанавливаем зависимости
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt


ENTRYPOINT ["/usr/src/APP/automigration.sh"]
