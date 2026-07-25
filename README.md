# LinuxTeacher5-PKGS
 Размещаем свой RPM в своем репозитории, ДЗ №5

Создал аккаунт на GitHub - https://github.com/

Предварительно установленное и настроенное следующее ПО:

ПК на Linux c 16 ГБ ОЗУ или виртуальная машина с системой Ubuntu.

Oracle VirtualBox (https://www.virtualbox.org/wiki/Linux_Downloads).

Все дальнейшие действия были проверены при использовании VirtualBox 7.2.6 r172322, хостовая ОС: Ubuntu 24.04 Desktop. 

Гостевая система — Ubuntu 24.04.4 LTS.

Оформить отчет в README-файле в GitHub-репозитории.

Цель домашнего задания: Создать свой DEB пакет, так каку меня Ubuntu

Сборка из исходников

В моем примере я возьу исходники для сборки nginx (для выполнения configure, make, make install ...) и соберу из них свой пакет для установки NGINX. 

Процесс будет разбит на несколько этапов

Устанавливаем пакеты:

<img width="808" height="262" alt="image" src="https://github.com/user-attachments/assets/486b5899-97a4-411a-902a-0ec3b2449746" />

Создам пользователя, из под которого будет собираться пакет

<img width="799" height="66" alt="image" src="https://github.com/user-attachments/assets/2bcbd6ec-c7be-4fe9-8b51-e57f50eeddf4" />

И захожу под этим пользователем в систему, все дальнейшие дествия буду выполнть от него

<img width="791" height="20" alt="image" src="https://github.com/user-attachments/assets/efafd73a-d4b4-419c-b65d-414326329b30" />

Создам каталог для сборки

<img width="806" height="51" alt="image" src="https://github.com/user-attachments/assets/19de1a79-c136-4632-bdf4-230d75b95f22" />

Подготовка

Создаv каталог с названием собираемого приложения (с учетом версии)

<img width="797" height="50" alt="image" src="https://github.com/user-attachments/assets/b94c58e7-85c0-4fb1-9828-6fa8f1466695" />

Результат:

<img width="788" height="171" alt="image" src="https://github.com/user-attachments/assets/bbf890a9-b541-4f1c-834f-8ff9561aa781" />

Перейду в каталог:

<img width="796" height="63" alt="image" src="https://github.com/user-attachments/assets/71fb2a2f-9888-4840-a335-32b1a4800a25" />

Создам файы сборки (основные)

Для выполнения сборки нужно создать, минимум, 4 файла.

Control-файл.

Содержание:

<img width="802" height="18" alt="image" src="https://github.com/user-attachments/assets/4d35ebf9-9505-4ba3-9603-e2da0988c30a" />

<img width="785" height="273" alt="image" src="https://github.com/user-attachments/assets/b433f0fa-104a-4a13-b643-d83c747419ac" />

Файл changelog

Содержание:

<img width="794" height="140" alt="image" src="https://github.com/user-attachments/assets/0b747fc4-00f0-45e9-96ca-dcad145fb951" />

Файл rules.

Содержание:

<img width="799" height="389" alt="image" src="https://github.com/user-attachments/assets/b4d4113a-d937-421a-b2a9-3860817de4e4" />

Файл compat.

Содержание:

<img width="798" height="116" alt="image" src="https://github.com/user-attachments/assets/a0180b1a-d6b2-49e0-8468-3d4da96811e3" />

Дополнительные файлы сборки

Данные файлы не являются обязательными. Они могут увеличить возможности собираемого пакета, а также нужны для удобства.

1. Файл postinst.

<img width="792" height="168" alt="image" src="https://github.com/user-attachments/assets/bf057a15-241f-40c5-8b8a-e1681667b709" />

2. Файл postrm.

Cкрипт, который выполнится после удаления пакета:

<img width="590" height="295" alt="image" src="https://github.com/user-attachments/assets/eb630e9d-2402-4526-9591-877c16014a07" />

3. Файл preinst.

<img width="797" height="278" alt="image" src="https://github.com/user-attachments/assets/6b73aaca-e159-479c-b8f8-2af4d4719b6a" />

4. Файл prerm.

<img width="770" height="276" alt="image" src="https://github.com/user-attachments/assets/1353966c-db60-4776-acc4-af22e02b73a2" />

Сборка пакета

У меня созданы все необходимые файлы, выполнены предварительные действия, и готов сборке. 

Проверю, что у меня установлены необходимые пакеты и, при необходимости, установлю их:

<img width="808" height="971" alt="image" src="https://github.com/user-attachments/assets/78b0b73a-038a-41c3-8109-15594eb7f5de" />

<img width="796" height="574" alt="image" src="https://github.com/user-attachments/assets/0278a885-36bb-428e-955d-c80856902cfd" />

Выполню сборку командой:

- начало сборки

<img width="792" height="975" alt="image" src="https://github.com/user-attachments/assets/d65e3c8d-9be1-4156-b999-b9b8a947050b" />

- процесс
 
<img width="796" height="976" alt="image" src="https://github.com/user-attachments/assets/f76c0d28-37ce-4e4d-b91f-ce68fc4d3d91" />

<img width="797" height="690" alt="image" src="https://github.com/user-attachments/assets/f95f38c6-5623-482a-b948-126d61207091" />

<img width="799" height="786" alt="image" src="https://github.com/user-attachments/assets/ff660f84-e704-4502-a2ae-1929e2741843" />

Вроде все правильно:

<img width="800" height="110" alt="image" src="https://github.com/user-attachments/assets/5b0c6ec4-6449-474e-901e-aa2b76a18ed9" />

<img width="795" height="21" alt="image" src="https://github.com/user-attachments/assets/7757a0c4-db2a-4f0d-a8b4-409631275724" />

Пакет **nginx_1.24.1_amd64.deb** сформирован и должен находится в директории на уровень ниже:

<img width="794" height="170" alt="image" src="https://github.com/user-attachments/assets/d172bbb9-6e30-4da7-8ef2-196b3fa8ec90" />

Установка и запуск сервиса при установке nginx пока локально на серверное ВМ, не через локальный репозиторий.

<img width="805" height="125" alt="image" src="https://github.com/user-attachments/assets/0966446e-bbd0-4bc1-8f78-bde2175821c4" />

Установлен и запущен. Отлично. 

Теперь удалим пакет nginx

<img width="811" height="96" alt="image" src="https://github.com/user-attachments/assets/23c5d54c-97e6-4356-b524-4ef44f94a805" />

Пакет удален. Отлично.

Теперь создам свой репозиторий и размещу там ранее собранный пакет Nginx для клиентов:

Создам папку для размещения файлов:

<img width="810" height="54" alt="image" src="https://github.com/user-attachments/assets/3c0f81cc-7374-4cc7-b82a-8316cb65f211" />

И скопирую в неё пакет Nginx:

<img width="810" height="83" alt="image" src="https://github.com/user-attachments/assets/5efd1c1e-1cea-4b3a-9dd1-7697a2deaca6" />

Перейду в локальный репозиторий и сгенирирую индексный файл пакетов:

<img width="772" height="82" alt="image" src="https://github.com/user-attachments/assets/ff104030-7520-4f0c-9388-6a3ceb21d1e9" />

Подключу репозиторий системе

<img width="812" height="70" alt="image" src="https://github.com/user-attachments/assets/d00ea3fd-260c-419b-b82d-885aac6dd228" />

И обновлю список пакетов.

Локальный репозиторий в системе:

<img width="671" height="808" alt="image" src="https://github.com/user-attachments/assets/dffb4575-3b23-4c2b-96c6-3556718b14f2" />

Установка **nginx**  через локальный репозиторий на севере:
<img width="811" height="440" alt="image" src="https://github.com/user-attachments/assets/8d58cd25-b49f-4339-b10e-2e3f9f590676" />

Настрою установленный Nginx для работы с локальным репозиторием

<img width="807" height="231" alt="image" src="https://github.com/user-attachments/assets/f179eeb5-0149-40a2-a523-366c376867a5" />






 


