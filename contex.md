# Контекст решения
<!-- Окружение системы (роли, участники, внешние системы) и связи системы с ним. Диаграмма контекста C4 и текстовое описание. 
-->
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

Person(admin, "Администратор")
Person(moderator, "Модератор")
Person(user, "Пользователь")

System(conference_site, "Мессенджер", "Веб-сайт для звонков и обмена сообщениями")

Rel(admin, conference_site, "Слежение за нарушителями правил мессенджера и законодательства в групповых чатах, блокировка аккаунтов")
Rel(moderator, conference_site, "Удаление сообщений, комментарий, нарушающие правила, предупреждение о нарушениях, рассылка сообщений от модераторов о новых обновлениях и напоминаниях о важности переодически менять пароль")
Rel(user, conference_site, "Регистрация, звонки, публикации сообщений в личных и групповых чатах")


@enduml
```

## Назначение систем
|Система| Описание|
|-------|---------|
| Мессенджер | Веб-интерфейс, обеспечивающий перессылку сообщений. Бэкенд сервиса реализован в виде микросервисной архитектуры |