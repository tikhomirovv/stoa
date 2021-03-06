# Техническое описание проекта

# 1. Цель проекта

Цель проекта — создать мобильное приложение с цитатами философов стоицизма. Показывает одну из цитат стоицизма на экране, с возможностью свайпать влево-вправо для переключения. Позволяет настроить уведомление с цитатой раз в день.

# 2. Описание системы

Регистрация не требуется. Приложение платное, фиксированная разовая оплата.

0. Профиль и настройки
1. Цитаты
2. Локализация (языки, часовой пояс)
3. Избранное
4. Настраиваемые уведомления
5. Ревью/онбординг
6. Виджет на iOS

- [Схема БД](https://whimsical.com/NbsrhsWuMqxPP8eCoUqR88)

## 2.0 Профиль и настройки

 - избранное
 - язык и таймзона
 - настройки уведомлений
 - оцените приложение
 - политика
 - правила и условия
 - о приложении
 - выход

## 2.1 Цитаты

Добавлять цитаты пока можно напрямую через БД, в админке нет необходимости. БД клиент — это и есть моя админка.

...

## 2.2 Локализация

Может потребоваться перевести приложения на другие языки. Нужно предусмотреть язык в архитектуре БД, а также сразу все тексты приложения прогонять через систему перевода, чтобы потом этим не заниматься.

Формат для установки языка/локали: ll-CC, где ll — это двух или трёхбуквенный код языка в нижнем регистре в соответствии со стандартом ISO-639, а CC — это код страны в соответствии со стандартом ISO-3166.

Так же нужно собирать таймзону пользователя для корректного отображения его даты, да и вообще, пусть будет, мало ли.

Формат таймзоны - полное название по базе данных часовых поясов IANA, например «America/New_York».

## 2.3 Избранное

Возможность сохранить какую-то цитату. В настройках уведомлений можно выбрать, показывать цитаты из избранного или все подряд.

## 2.4 Настраиваемые уведомления

Уведомления можно отсылать через OneSignal. Пользователь может включить или выключить уведомление, настроить его тип и время. Пока будет два типа: случайная цитата или из избранного.


## 2.5 Ревью / онбординг

При первом запуске приложения нужно показать вводный текст о том, что стоицизм прекрасен, ему 2000 лет, он поможет тебе стать спокойнее и счастливее. На первом же экране предложить включить уведомления.

## 2.6 Виджет на iOS

Этот пункт под вопросом — нужно сначала понять, есть ли такая возможность при разработке приложения на Flutter.

# 3. Стек технологий

 - Flutter/Dart
 - golang rest api
 - postgresql
 
#### Сторонние сервисы

 - OneSignal - отправка уведомлений

# 4. Требования к дизайну

Минималистичный, монохромный. За ориентир можно взять приложение `stoic.`.