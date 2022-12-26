<h1 align='center'>Автоматизация развёртывания и настройки Postfix. Настройка Dovecot.</h1>

<p>
    <strong>Шаг 1. </strong> Создание playbook для запуска роли
</p>
<p><i>Пример:</i></p>

<pre>
---
- name: Install and Settigx Postfix and Dovecot
  hosts: dovecot 
  become: true 

  roles: 
    - ansible-role-postfix-dovecot
</pre>

<p>
    <strong>Шаг 2. </strong> Склонировать роль в дирректорию с playbook:
</p>

  <pre>https://github.com/NewErr0r/ansible-role-postfix-dovecot.git</pre>

<p>

<p>
    <strong>Список переопределяемых переменных для playbook. </strong>
</p>
<pre>
#MariaDB
potsfixadmin_database_name: 'postfix'
postfixadmin_database_username: 'postfix'
postfixadmin_database_username_password: 'postfix123'
<br>
#Certificate common name (CN:)
hostname_server: 'dovecot'
</pre>

<p>
    <strong>Шаг 3. </strong> Запуск playbook:
</p>
<pre>
ansible-playbook -i inventory/hosts playbook.yml
</pre>
