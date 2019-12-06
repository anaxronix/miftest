Тестовая среда: любой Linux с docker и docker-compose

Напишите файл docker-compose.yml который будет описывать установку кластера из 4х нод. 

Структура кластера:
Балансировщик нагрузки nginx (miftest-b1)
Веб нода - 2 штуки (miftest-w1 и miftest-w2)
База данных mysql (miftest-db1)
PHP 7.3 (организовать запуск скриптов через socket)

Условия
Балансировщик равномерно распределяет нагрузку между 2мя веб нодами
Рабочая папка /var/www/htdocs (доступна для записи с хостовой машины)
В папке /var/www/htdocs лежит файл index.php который выводит phpinfo()
В папке /var/www/htdocs находится директория files в которой лежат несколько файлов (положите любые на ваше усмотрение)
Организована синхронизация файлов между веб нодами находящихся в папке htdocs/files (если закачать файл на miftest-w1/htdocs/files, то он появляется и на  miftest-w2/htdocs/files с минимальными задержками)
На miftest-w1 и miftest-w2 установлен nginx с конфигурацией запуска php скриптов через sockets
Обработка php файлов осуществляется через socket (не порт)
В php есть возможность отредактировать файл php.ini без пересборки контейнера
Все ноды друг друга видят и пингуются между собой
После перезапуска контейнера mysql, данные в базе не удаляются
Наружу открыт только 80/443 порт
Кластер автоматически разворачивается запуском docker-compose up -d