Lighthouse-role
=========

Роль устанавливает Lighthouse.

Требования к окружению
------------

rpm-based дистрибутив Linux (CentOS, RedHat).

Установленные пакеты:
- git
- wget
- curl
- unzip
- gnupg
- nginx

Переменные роли
--------------
```YAML
#Адрес репозитория Lighthouse
lighthouse_repo: "https://github.com/VKCOM/lighthouse.git"
#директория с Lighthouse
lighthouse_dir: "/var/www/{{ virtual_domain }}"
#Настройки для Nginx
#Число рабочих процессов.
worker_processes: auto
#максимальное число соединений, которые одновременно может открыть рабочий процесс
worker_connections: 2048
#максимально допустимый размер тела запроса клиента
client_max_body_size: 512M
#Имя пользователя Nginx
nginx_user: nginx
#название директории для Lighthouse
virtual_domain: lighthouse
```

Зависимости
------------

Нет

Пример playbook
----------------
```YAML
- name: Install lighthouse
  hosts: lighthouse
  become: yes
  become_user: root
  remote_user: vagrant
  roles:
    - lighthouse
  tags: lighthouse
```
License
-------

Free

Информация об авторе
------------------

Реализация: Дмитрий Багрянский
