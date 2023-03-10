# byte-of-pizza

# Посмотреть рабочий проект можно по этой ссылке https://pizza-admin.nulluall.repl.co/
+ добавиться в мой slack workspace по ссылке (высылаю в личку)
+ предварительно запустить код тут:
  + https://replit.com/@nullUall/pizza-byte#index.ts
  + https://replit.com/@nullUall/pizza-admin#server.ts



Чтобы запустить проект самостоятельно, понадобится:
+ аккаунт на https://www.cloudamqp.com/ и https://www.mongodb.com/cloud
+ заполнить .env файлы нужными ссылками на MQ и MongoDb
+ создать и настроить slack приложение, заполнить .env файл соответствующими значениями (есть задеплоенный бот тут https://replit.com/@nullUall/pizza-byte#index.ts)
+ готовый к запуску backend и frontend админки есть тут https://replit.com/@nullUall/pizza-admin#server.ts
+ чтобы посмотреть все в работе достаточно запустить код на двух "реплитах" 

# Настройка Slack приложения

нужно:
+ включить socket-mode
+ включить event-subscriptions
+ включить Interactivity & Shortcuts
+ во вкладке "OAuth & Permissions" нужны Bot Token Scopes
  + chat:write
  + im:history
  + app manifest выглядит примерно так:
  
  ```yaml
    display_information:
    name: pizza-byte
    description: Bot for ordering a byte of pizz
    background_color: "#413b2b"
  features:
    bot_user:
      display_name: bit-pizza
      always_online: false
  oauth_config:
    scopes:
      bot:
        - chat:write
        - im:history
  settings:
    event_subscriptions:
      request_url: https://pizza-byte.nulluall.repl.co/slack/events
      bot_events:
        - message.im
    interactivity:
      is_enabled: true
    org_deploy_enabled: false
    socket_mode_enabled: true
    token_rotation_enabled: false


