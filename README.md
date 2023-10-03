# Linux_Lesson_37
## LDAP
### Описание репозитория
Лабораторный стенд для тестирования LDAP.

- **Vagrantfile** - создает три виртуальных машины на основе CentOS 8, подлюченные к единой сети: сервер LDAP и два клиентских хоста.  
> [!WARNING]
> Для установки FreeIPA сервер необходимо не менне 2 Гб оперативной памяти.  
- **provision.yml** - основной файл Ansible playbook для установки и настройки сетевых устройстввиртуальных машин стенда.  
- **hosts** - файл для быстрого доступа к виртуальным машинам из playbook.  
На сервере LDAP устанавливается и настраивается сервер FreeIPA, на хостах - клиентские части. Управление участниками LDAP может производится из консоли непосредственно на сервере или с использованием веб-интерфейса.
> [!IMPORTANT]
> Для подключения с хостовой машины с помощью браузера к веб-интерфейсу сервера FreeIPA необходимо в файле /etc/hosts прописать его соответствие:  
    192.168.57.10 ipa.otus.lan

---

### Проверка работоспособности стенда
