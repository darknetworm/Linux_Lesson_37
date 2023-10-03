# Linux_Lesson_37
## LDAP
### Описание репозитория
Лабораторный стенд для тестирования LDAP.

- **Vagrantfile** - создает три виртуальных машины на основе CentOS 8, подлюченные к единой сети: сервер LDAP и два клиентских хоста.  
> [!WARNING]
> Для установки сервера FreeIPA необходимо не менне 2 Гб оперативной памяти.  
- **provision.yml** - основной файл Ansible playbook для установки и настройки виртуальных машин стенда.  
- **hosts** - файл для быстрого доступа к виртуальным машинам из playbook.  
На сервере LDAP устанавливается и настраивается сервер FreeIPA, на хостах - клиентские части. Управление участниками LDAP может производится из консоли непосредственно на сервере или с использованием веб-интерфейса.
> [!IMPORTANT]
> Для подключения с хостовой машины с помощью браузера к веб-интерфейсу сервера FreeIPA необходимо в файле /etc/hosts прописать его соответствие:
> 
    192.168.57.10 ipa.otus.lan

---

### Проверка работоспособности стенда
На сервере IPA просматриваем записи пользователей с помощью команды:  

        ipa user-find --all

Результат работы представлен в виде файла kuser.txt.

Наличие записей о созданных пользователях FreeIPA проверяется с помощью веб-интерфейса   
![users](https://github.com/darknetworm/Linux_Lesson_37/assets/82410807/e7471801-0f7a-404a-8bec-b1693d97b8c9)

Наличие записей о подключенных к FreeIPA хостах также проверяется с помощью веб-интерфейса  
![hosts](https://github.com/darknetworm/Linux_Lesson_37/assets/82410807/c0314c21-52f0-41fc-831b-ee5c2c67479b)

Для подключения к LDAP серверу с клиентских хостов используется Kerberos-инициализация, подключение к серверу по ssh и проверка текущей директории
На хосте client1.otus.lan  
![user1](https://github.com/darknetworm/Linux_Lesson_37/assets/82410807/623793f0-a7b3-4316-88d1-f5f29a68b573)

На хосте client2.otus.lan  
![user2](https://github.com/darknetworm/Linux_Lesson_37/assets/82410807/e2314ed4-3ee0-45f2-96ac-b05360556a2d)
