# Project-Server TehnoMagiсRPG 1.20.1

Этот проект состоит из трех частей, каждая из которых находится в отдельном репозитории:

1. **Server**: Содержит серверную часть проекта.
   - Ссылка на репозиторий: https://github.com/Xemul-lab/server
   - Как скачать: [Скачать ZIP](https://github.com/Xemul-lab/server/releases/download/v1.0/server.1.20.1.zip)

2. **Mods**: Содержит модификации для проекта.
   - Ссылка на репозиторий: https://github.com/Xemul-lab/mods
   - Клиентская часть: [Скачать ZIP](https://github.com/Xemul-lab/mods/releases/download/v1.0/for.client.zip)
   - Серверная часть: [Скачать ZIP](https://github.com/Xemul-lab/mods/releases/download/v1.0/for.server.zip)
3. **Resourcepacks**: Содержит пакеты ресурсов для проекта. 
   - Ссылка на репозиторий: https://github.com/Xemul-lab/resourcepacks
   - Как скачать: [Releases](https://github.com/Xemul-lab/resourcepacks/releases/tag/v1.0)

Каждый из этих репозиториев можно скачать отдельно, в зависимости от ваших потребностей.









# Инструкция по Project‑Server для Windows

1. Требования

Перед началом убедись, что у тебя есть:

Java 17 или выше (для Minecraft 1.20.1)

Minecraft Forge 1.20.1 (серверная версия)

Git (или скачивание ZIP через браузер)

Минимум 8 ГБ RAM для стабильного запуска сервера с модами

2. Скачивание репозиториев

Создай папку, куда будешь распаковывать все файлы. Например:

D:\Minecraft\Project-Server\

Скачай все необходимые репозитории:

Server: https://github.com/Xemul-lab/server

Mods: https://github.com/Xemul-lab/mods

Resourcepacks: https://github.com/Xemul-lab/resourcepacks

Можно клонировать через Git (если установлен):
cd D:\Minecraft\Project-Server
git clone https://github.com/Xemul-lab/server.git
git clone https://github.com/Xemul-lab/mods.git
git clone https://github.com/Xemul-lab/resourcepacks.git

3. Структура папок после скачивания

D:\Minecraft\Project-Server\
    server\             ← файлы сервера
        mods\           ← сюда кладём серверные моды
        config\         ← конфиги модов и сервера
        forge-1.20.1-xxx.jar  ← Forge server jar
        start.bat       ← скрипт для запуска сервера
    mods\
        client\         ← клиентские моды
        server\         ← серверные моды (копируем в server/mods/)
    resourcepacks\      ← ресурспаки (текстуры, модели)
    
4. Установка модов на сервер

   1. Перейди в папку mods/server/ из репозитория mods.
   2. Скопируй все .jar файлы в папку:

   D:\Minecraft\Project-Server\server\mods\
   
   4. Скопируй конфиги модов (если они есть) из mods/server/config/ → в server/config/.
      
5. Настройка Forge сервера
   1. Убедись, что в папке server есть Forge server jar (например: forge-1.20.1-47.4.0.jar).
   2. Создай скрипт запуска start.bat (если его нет) с содержимым:

@echo off
java -Xmx8G -Xms8G -jar forge-1.20.1-47.4.0.jar nogui
pause

-Xmx8G — максимальная память (замени на своё значение)
-Xms8G — начальная память
   3. Сохрани файл start.bat в папке server/.
   
6. Первый запуск сервера

   1. Дважды кликни на start.bat → сервер начнёт запуск.
   2. После первой загрузки появится файл eula.txt.
   3. Открой eula.txt и измените: eula=false на eula=true
   4. Снова запусти start.bat. Сервер будет полностью готов.
   
7. Настройка server.properties
   Проверь порт (по умолчанию 25565)
   Установи максимальное количество игроков
   Можно настроить мир, спавн мобов и другие параметры
   
9. Настройка клиента Minecraft
   1. В папку mods/client/ положи клиентские моды:

   %appdata%\.minecraft\mods\

   2. Установи Forge клиента той же версии (1.20.1).
   3. Скопируй ресурспаки из resourcepacks/ в:

   %appdata%\.minecraft\resourcepacks\

   4. Включи ресурспаки в настройках Minecraft → «Настройки → Ресурспаки».

9. Подключение к серверу

   1. Запусти сервер (start.bat).
   2. Открой Minecraft → Multiplayer → Add Server.
    Введи:
    Server Name: любое удобное имя
    Server Address: localhost (если на той же машине)
    Server Address: IP вашего компьютера в Radmin VPN (например 26.18.1.2)
    Port: 25565
   4. Подключись и играй с модами и ресурс-паками.
