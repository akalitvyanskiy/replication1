# Домашнее задание к занятию «Репликация и масштабирование. Часть 1» - Калитвянский Александр SYS-27

### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.

---

### Задание 1

На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия.

*Ответить в свободной форме.*

Репликация типа Master-Slave часто используется для обеспечения отказоустойчивости приложений. Кроме этого, она позволяет распределить нагрузку на базу данных между несколькими серверами, или репликами. В этом подходе выделяется один основной сервер базы данных, который называется Master. На нем происходят все изменения в данных (любые запросы MySQL INSERT/UPDATE/DELETE). Слейв сервер постоянно копирует все изменения с Master. С приложения на Слейв сервер отправляются запросы чтения данных (запросы SELECT). Таким образом Master сервер отвечает за изменения данных, а Slave за чтение.
Репликация типа Master-Master: в ней любой из серверов может использоваться как для чтения, так и для записи.  
Существует мнение о проблематичности репликации  Master-Master. Аргументацией стороников данного мнения является что выход из строя одного из серверов практически всегда приводит к потере каких-то данных. Последующее восстановление также сильно затрудняется необходимостью ручного анализа данных, которые успели либо не успели скопироваться.

---

### Задание 2

Выполните конфигурацию master-slave репликации, примером можно пользоваться из лекции.

*Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.*

Master:  
![Скриншот 1](https://github.com/akalitvyanskiy/replication1/blob/main/img/2.png)
![Скриншот 2](https://github.com/akalitvyanskiy/replication1/blob/main/img/21.png)
![Скриншот 3](https://github.com/akalitvyanskiy/replication1/blob/main/img/22.png)
![Скриншот 4](https://github.com/akalitvyanskiy/replication1/blob/main/img/23.png)
![Скриншот 5](https://github.com/akalitvyanskiy/replication1/blob/main/img/24.png)  

Slave:  
![Скриншот 6](https://github.com/akalitvyanskiy/replication1/blob/main/img/25.png)
![Скриншот 7](https://github.com/akalitvyanskiy/replication1/blob/main/img/26.png)  

Master:  
![Скриншот 8](https://github.com/akalitvyanskiy/replication1/blob/main/img/27.png)  

Slave:  
![Скриншот 9](https://github.com/akalitvyanskiy/replication1/blob/main/img/28.png)
![Скриншот 10](https://github.com/akalitvyanskiy/replication1/blob/main/img/29.png)
![Скриншот 11](https://github.com/akalitvyanskiy/replication1/blob/main/img/291.png)
![Скриншот 12](https://github.com/akalitvyanskiy/replication1/blob/main/img/292.png)  

Master:  
![Скриншот 13](https://github.com/akalitvyanskiy/replication1/blob/main/img/293.png)
![Скриншот 14](https://github.com/akalitvyanskiy/replication1/blob/main/img/294.png)  

Slave:  
![Скриншот 15](https://github.com/akalitvyanskiy/replication1/blob/main/img/295.png)
![Скриншот 16](https://github.com/akalitvyanskiy/replication1/blob/main/img/296.png)  

---

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

---

### Задание 3* 

Выполните конфигурацию master-master репликации. Произведите проверку.

*Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.*

