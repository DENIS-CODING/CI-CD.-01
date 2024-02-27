# CI-CD.-01
CI/CD. Семинар 01

Задача
Зарегистрироваться на gitlab.com
Создать pipeline и runner
Попробовать сохранить артефакт одной из стадий + исключить из папки с артефактами любой файл
Попробовать сделать любую gitlab pages


Решение

image: alpine:latest

pages:
  stage: deploy
  script:
  - echo 'First page 01'
  - mkdir .public
  - cp -r * .public
  - mv .public public
  artifacts:
    paths:
    - public
    exclude:
    - public/file_to_exclude.md
  only:
  - master


Исключение файла из папки с артефактами:
...
  artifacts:
    paths:
    - public
    exclude:
    - public/file_to_exclude.md
...





