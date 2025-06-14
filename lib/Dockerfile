FROM ubuntu:20.04

# Установка системных зависимостей
RUN apt-get update && apt-get install -y \
    git \
    python3-pip \
    locales \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Обновление pip и setuptools
RUN python3 -m pip install --upgrade pip setuptools

# Настройка локали
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

# Создание рабочей директории
WORKDIR /app

# Копирование и установка зависимостей
COPY requirements.txt .
RUN pip install -r requirements.txt

# Копирование всего проекта
COPY . .

# Установка PYTHONPATH чтобы Python видел ваш проект
ENV PYTHONPATH="/app:${PYTHONPATH}"

# Установка вашего пакета (если нужно)
RUN pip install -e .