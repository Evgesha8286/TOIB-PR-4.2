# TOIB-PR-5 
# Практическое задание на тему "Контроль целостности"
Выполнил студент группы: ББМО-02-23 Панков Евгений Ромуальдович
## Установка и запуск виртуальной машины с Astra linux
Для выполнения данного задания был скачан образ Astra Linux ( ссылка: https://1drv.ms/u/s!Ap1Ijs338IQ9gZFmLJ5hn45FgcVLoQ?e=mH7Jzg ) и установлена версия системы "Смоленск" с максимальным уровнем защиты

![image](Screenshots/1.png)

### Установка, настройка и проверка мандатного контроля целостности
##Для установки МКЦ в ОС Astra Linux выбираем указанные галочки в процессе установки ISO образа 

![image](Screenshots/2.png)

## Для измнения конфигурации МКЦ в Astra Linux необходимо запустить утилиту "Управление политикой безопасности"

![image](Screenshots/3.png)

## В меню "Режим эксперта" назначаем уровни целостности для директорий. В качестве проверки правила NWU обозначили 2 тестовые директории ("Музыка" и "Видео") с  правами:

![image](Screenshots/4.png)

## Проверяем настройку мандатного контроля зайдя в учетную запись с атрибутом целостности на уровне "Низкий".

## Пример взаимодействия (записи) между тестовыми директориями:

![image](Screenshots/5.png)

Здесь можно увидеть, что копирование файла с атрибутом ниже в папку с атрибутом выше не сработало - была получена ошибка доступа. В то же время "запись вниз" работает.
### Работа с режимом замкнутой программной среды
## Проверка работы режима ЗПС в утилите "Управлении политикой безопасности" посредством включения настроек:

![image](Screenshots/6.png)

## В качестве тестового файла был взят скрипт инициализации AnyDesk. Результат выполнения:

![image](Screenshots/7.png)

### Работа с утилитами контроля целостности и регламентного контроля целостности
## Использование `gostsum`
Утилита `gostsum` вычисляет хэш-сумму файлов в соответствии с ГОСТ Р 34.11-2012. Пример использования с .deb пакетом:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/28319cd6-906e-45b7-b37e-f003f554f4af)<br />
## Использование `afick`
`afick` - утилита, предназначенная для контроля целостности файловой системы ОС. Для корректной работы утилиты сначала создается БД утилиты:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/194b9811-8df0-480e-b965-f9f8ccdcfd3d)<br />
## Далее изменим часть системных файлов для получения ответа от утилиты, перед этим сделав бэкап:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/42844996-839a-4a3a-8b71-da86431ecc26)<br />
## Получаем результат от утилиты:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/e4572623-ba08-4c70-82ca-03635c309392)<br />
