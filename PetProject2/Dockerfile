FROM python:3.10
# Рабочая директория внутри проекта
WORKDIR /usr/src/APP
# Переменный пайтона
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
# Устанавливаем зависимости для Postgre
RUN apt-get update -y && apt-get upgrade -y && pip install --upgrade pip
RUN apt-get install -y netcat-traditional

# устанавливаем зависимости
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# копируем содержимое текущей папки в контейнер
COPY . .

ENTRYPOINT ["/usr/src/APP/automigration.sh"]
