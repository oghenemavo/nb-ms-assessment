
# Next Basket Microservice Assessment

This project is built with symfony 6, it comprises of two Microservices: Onboarding and Notifications. The Onboarding service creates a user and stores the data in a file sending signals to the Notifications service using RabbitMQ


## Installation

Clone the repository which contains two services: Onboarding and notifications

build and run the rabbitmq image on docker

```bash
  docker run -d --hostname rmq --name rabbit-server -p 8080:15672 -p 5672:5672 rabbitmq:3-management
```

bootstrap the onboarding and notification services

```bash
  cd onboarding_service
  composer install
  symfony server:start
```

```bash
  cd notifications_service
  composer install
  php bin/console messenger:consume -vv
```
    