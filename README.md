# TOIB-PR-5 
# Практическое задание на тему "Контроль целостности"
# Выполнил студент группы: ББМО-02-23 Панков Евгений Ромуальдович
## Установка и запуск виртуальной машины с Astra linux
Для выполнения данного задания был скачан образ Astra Linux и установлена версия системы "Смоленск" с максимальным уровнем защиты<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/dd2474bf-1945-4491-b9a9-89bdf3c48ad4)
## Настройка и проверка мандатного контроля целостности
Для измнения конфигурации МКЦ в ОС Astra Linux необходимо воспользоваться утилитой Управление политикой безопасности<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/3f9efe8b-5841-4de7-8d4c-f94a447bb950)<br />
В меню Режим эксперта можно непосредственно назначить уровни целостности для директорий. В качестве проверки правила NWU я обозначил 2 тестовые директории с такими правами:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/01ce3f1e-0bbe-423b-b0e2-52478c529167)<br />
Для проверки мандатного контроля необходимо зайти в учетную запись с атрибутом целостности уровня "Низкий".<br />
Ниже представлен пример взаимодействия по записи между обеими папками<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/83a96e21-73cf-4ce4-85be-d07589a70524)<br />
Здесь можно увидеть, что копирование файла с атрибутом ниже в папку с атрибутом выше не сработало - была получена ошибка доступа. В то же время "запись вниз" работает.
## Работа с режимом замкнутой программной среды
Для проверки работы режима ЗПС в Управлении политикой безопасности необходимо включить данные настройки:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/460cd4ed-124a-4e04-9194-fdd73c99b0fe)<br />
В качестве тестового файла я взял скрипт для установки VMWare Tools. Результат выполнения на скриншоте:<br /><br />
![Astra-2023-11-22-14-39-36](https://github.com/kirasir1/toib_prak/assets/13931629/307ebee8-ba43-4d0b-9d83-c9a1da34daca)<br />
## Работа с утилитами контроля целостности и регламентного контроля целостности
### Использование `gostsum`
Утилита `gostsum` вычисляет хэш-сумму файлов в соответствии с ГОСТ Р 34.11-2012. Пример использования с .deb пакетом:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/28319cd6-906e-45b7-b37e-f003f554f4af)<br />
### Использование `afick`
`afick` - утилита, предназначенная для контроля целостности файловой системы ОС. Для корректной работы утилиты сначала создается БД утилиты:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/194b9811-8df0-480e-b965-f9f8ccdcfd3d)<br />
Далее изменим часть системных файлов для получения ответа от утилиты, перед этим сделав бэкап:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/42844996-839a-4a3a-8b71-da86431ecc26)<br />
Получаем результат от утилиты:<br /><br />
![изображение](https://github.com/kirasir1/toib_prak/assets/13931629/e4572623-ba08-4c70-82ca-03635c309392)<br />
