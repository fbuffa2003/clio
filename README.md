Bpmonline Command Line Interface (bpmcli)
=============================

Проект предназначен для интеграции систем разработки и CI/CD
c платформой bpmonline версии 7.13.0 и выше

Возможности bpmcli:
* Перезапуск приложения
* Формирование пакета из файловой системы
* Установка пакета в приложение
* Загрузка/выгрузка контента пакета в приложение при работе в РФС
* Выполнение кода сборки в приложении
* Установка пакета из архива

INSTALLATION
---------------------
### Setup


COMMANDS
---------------------

### Перезапуск приложения

Перезапуск приложения с выгрузкой домена

```powershell
bpmcli restart
```
### Настройка окружения

Создание нового окружения: имя , путь к сайту, логин и пароль для подключения
```powershell
bpmcli cfg -e dev -u http://mysite.bpmonline.com -l user -p pa$$word
```
Установка окружения по умолчанию
```powershell
bpmcli cfg -a dev
```
Измененение параметра существущего окружения
```powershell
bpmcli cfg -e dev -p pa$$word
```

Удаление окружения
```powershell
bpmcli remove -e dev
```

Использование неосновного окружения при вызове команд

```powershell
bpmcli restart -e dev
```

### Использование в CI\CD

В системах CI\CD можно не использовать файл конфигурации и передавать параметры
напрямую при каждом вызове команды

```powershell
bpmcli restart -u http://mysite.bpmonline.com -l administrator -p pa$$word
```

### Установка пакета из архива

```powershell
bpmcli install -f путь_к_файлу\SalesEnterprise.zip
```

### Сжатие проекта в пакет
```powershell
bpmcli compress -s путь_к_папке_проекта\ -d путь_к_файлу\file.gz
```