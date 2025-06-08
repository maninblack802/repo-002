# Домашнее задание к занятию "Gitlab" - `Хоружий Артем`

### Задание 1

`В качестве ответа в репозиторий шаблона с решением добавьте скриншоты с настройками раннера в проекте`

![image](https://github.com/maninblack802/repo-002/blob/main/img/image.png)


### Задание 2

`В качестве ответа в шаблон с решением добавьте скриншоты с успешно собранными сборками`

stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script:
  - echo "Start test"
  - go test .
  tags:
  - netology

build:
  stage: build
  image: docker:24.0.2
  services:
  - name: docker:dind
    alias: docker
  variables:
    DOCKER_HOST: "tcp://docker:2375"
    DOCKER_TLS_CERTDIR: ""
  script:
  - echo "Start build"
  - docker build .
  tags:
  - netology

![image1](https://github.com/maninblack802/repo-002/blob/main/img/image1.png)
![image2](https://github.com/maninblack802/repo-002/blob/main/img/image2.png)
![image3](https://github.com/maninblack802/repo-002/blob/main/img/image3.png)
