# myasoedova
Для установки утилиты wget вводим команду `sudo yum istall wget` мы получаем ошибку is not a sudoers file. Для исправления данной ошибки была введена команда `su root` для входа с правами администратора, после этого был введен пароль администратора.

![image](https://github.com/user-attachments/assets/ae86b4d9-31da-421b-b5d0-8381be150399)

Была введена команда `vi /ets/sudoers` с помощью которой открывается редактор. В котом мы переписали значения из строки root, заменив его на имя пользователя, предварительно нажав кнопку insert. После этого что бы выйти из редактора с сохранением изменений нужно нажать `Esc`, `Shift + ;` и ввести `W`, `Q!`. Что бы выйти без сохранения нужно нажать `Esc` `Shift + ;` и ввести `Q!` .

![image](https://github.com/user-attachments/assets/ee5b7131-5074-4649-bd00-981b8efdf483)

После выхода из редактора была введена команда `sudo yum install wget` и введен пароль администратора. После этого у нас происходит установка утилиты wget, которая позволяет загружать файлы из сети.
![image](https://github.com/user-attachments/assets/21d51efb-75d4-44d3-9622-c30471e725ed)


Команда `sudo wget -P /etc/yum.repos.d/` используется для автоматического скачивания конфигурационного файла репозитория в директорию `/etc/yum.repos.d/`. С помощью этой команды мы скачиваем Docker.
![image](https://github.com/user-attachments/assets/00127a8e-4e93-42d6-a5d6-98c5a3584c06)

С помощью команды `sudo yum install docker-ce docker-ce-cli containerd.io` устанавливает пакет в систему с помощью пакетного менеджера yum.

![image](https://github.com/user-attachments/assets/64c82193-76bc-4b9a-a038-aeb200128d49)
![image](https://github.com/user-attachments/assets/844d4c1b-b4e7-4789-8758-f261d850cfe6)

С помощью команды `sudo systemctl enable docker --now` настроится автоматический запуск Docker при старте системы.
![image](https://github.com/user-attachments/assets/68e77201-745c-4c3f-b405-7bccfb4f3bd4)


Команда `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)` извлекает и сохраняет в переменной `COMVER` номер версии последнего релиза Docker Compose. 
![image](https://github.com/user-attachments/assets/bce728d6-8fa7-45a8-9399-f51d9aa22575)

С помощью команды `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose` загружаем файл Docker Compose для определённой версии и сохраняем его в системную директорию.
![image](https://github.com/user-attachments/assets/3b2a991b-974b-4e7e-99d4-7618c4bbf930)

Команда `sudo chmod +x /usr/bin/docker-compose` используется для изменения прав доступа к файлу `docker-compose`. Команда `docker-compose --version` используется для просмотра версии Docker Compose.
![image](https://github.com/user-attachments/assets/c805d966-c505-4261-9143-113126fea09a)

Команда `git clone` используется для создания копии удаленного репозитория.
![image](https://github.com/user-attachments/assets/ed5e06a3-5aee-4286-96f3-e28d93d2ef08)

Команда `cd grafana_stack_for_docker` используется для перехода в репозиторий grafana_stack_for_docker. Команда `sudo mkdir -p /mnt/common_volume/swarm/grafana/config` создала всю необходимую иерархию каталогов и сам каталог `config`.
![image](https://github.com/user-attachments/assets/42141dc6-cd2a-45a1-859c-2afb8df1cac8)

Команда `sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}` выполняет создание нескольких директорий.

![image](https://github.com/user-attachments/assets/b9bf28ec-1204-4255-afce-ab3a1d188db6)

Команда `sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}` менять владельца и группу для всех файлов и каталогов в `/mnt/common_volume/swarm/grafana/config` и `/mnt/common_volume/grafana` на текущего пользователя.

![image](https://github.com/user-attachments/assets/5759217a-800b-4b6e-b9c2-505f5c458bc6)

Команда  `touch /mnt/common_volume/grafana/grafana-config/grafana.ini` обновит временные метки доступа и изменения файла `grafana.ini` на текущее время

![image](https://github.com/user-attachments/assets/ac659341-9181-41f7-a788-96e62185b128)

Команда `cp config/* /mnt/common_volume/swarm/grafana/config/` используется для копирования файлов конфигурации Grafana.

![image](https://github.com/user-attachments/assets/87a00f0d-f9bf-42d4-8bff-640dd841003f)

Команда `mv grafana.yaml docker-compose.yaml` используется для переименования файла grafana.yaml в docker-compose.yaml.

![image](https://github.com/user-attachments/assets/f0ef921b-c058-4740-8c26-48051c240b2a)

Команда `docker-compose up -d` используется для запуска контейнеров в фоновом режиме.
![image](https://github.com/user-attachments/assets/829e51f6-d39b-48a4-b22c-08aeab252aec)
