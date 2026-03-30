# Flask + Redis на Kubernetes (Minikube)

## 📋 Описание
Веб-приложение на Flask с подключением к Redis для подсчёта посещений, развёрнутое в Kubernetes кластере через Minikube.

## 📁 Структура проекта
flask_redis_k8s/
├── flask_redis/ # Исходный код приложения
│ ├── app.py # Flask приложение
│ ├── Dockerfile # Инструкция для сборки образа
│ └── requirements.txt # Python зависимости
├── k8s/ # Kubernetes манифесты
│ ├── flask.yml # Deployment Flask (5 реплик)
│ ├── flask-service.yml # Service Flask (LoadBalancer)
│ ├── redis.yml # Deployment Redis (1 реплика)
│ └── redis-service.yml # Service Redis (ClusterIP)
├── screenshots/ # Скриншоты выполнения
└── README.md


## 🛠 Требования

- VirtualBox 7.x
- Ubuntu 24.04 VM
- Minikube 1.38+
- kubectl
- Docker

## 🚀 Быстрый старт

```bash
# Запуск Minikube
minikube start

# Применение манифестов
kubectl apply -f k8s/

# Проверка статуса
kubectl get pods
kubectl get services

# Доступ к приложению
minikube tunnel
curl http://10.0.2.15:8000
