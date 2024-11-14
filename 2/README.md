### Лабораторная работа №2


> Цель работы
>> Запустить приложение при помощи ansible, научиться писать плейбуки и пользоваться group vars
> 
>> Docker-образ: https://hub.docker.com/repository/docker/timurbabs/django
> 
> 
>> Репозиторий с docker role [ссылка] (https://github.com/Hacker-zen/DevOpsRoles)
>>
>> 
>> Универсальный файл для вагранта: [Vagrantfile](https://drive.google.com/file/d/1Q5deuz9kcm9VeXDiX44iuHZZSp66VuAY/view)
>> 
> Задачи:
>> * Инициировать структуру роли “Docker” через Ansible-Galaxy
>> * Вынести из предыдущего плейбука задачи установки Docker в отдельную роль
>> * Параметризовать роль через переменные
>> * Создать в gitlab группу для репозиториев с ролями, запушить роль “Docker” в репозиторий
>> * Создать файл requirements.yml для установки роли Docker из репозитория
>> * Запустить приложение на нодах группы [app] используя ansible-playbook с ролью “Docker”


