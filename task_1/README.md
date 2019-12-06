- Тестовая среда: Ubuntu Linux 18.04 с правами по ssh root
- Запуск из каталога: ansible-playbook -i hosts base.yml -k

Напишите ansible playbook для автоматической установки nginx + jenkins.
Условия:
Маршрутизировать доступ до jenkins через nginx
Jenkins не должен быть доступен извне на своем порту
При повторном запуске playbook, ничего не должно переустанавливаться. Если удалить nginx и запустить playbook соответственно, должен переустановиться nginx.
