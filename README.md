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

<img width="798" height="143" alt="image" src="https://github.com/user-attachments/assets/7e326c1f-02d1-413a-a19e-d63c1b92de47" />

2. Файл postrm.

Cкрипт, который выполнится после удаления пакета:

<img width="798" height="356" alt="image" src="https://github.com/user-attachments/assets/dbd837a2-739e-4bd0-a756-79fe6405e1ea" />

3. Файл preinst.

<img width="797" height="278" alt="image" src="https://github.com/user-attachments/assets/6b73aaca-e159-479c-b8f8-2af4d4719b6a" />

4. Файл prerm.

<img width="798" height="341" alt="image" src="https://github.com/user-attachments/assets/75a56cbf-9668-45a5-836e-ced2c0fc43dc" />

Сборка пакета

У меня созданы все необходимые файлы, выполнены предварительные действия, и готов сборке. 

Проверю, что у меня установлены необходимые пакеты и, при необходимости, установлю их:



