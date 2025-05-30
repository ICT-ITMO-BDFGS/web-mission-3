# Mission 2  
## Part 0  

[Link to video](https://drive.google.com/file/d/1mRZqqs4yaCemId1KiuaC-j3sow4oEd4i/view?usp=drive_link)  

## Part1  
 
- Зачем нужен ssh? Ответ на пару предложений.
> SSH нужен для безопасного удалённого доступа к серверам и управления ими через зашифрованное соединение. Он позволяет выполнять команды, передавать файлы и обеспечивает защиту данных от перехвата.

- Предположим, у вас есть прямой доступ к серверу(терминалу) под управлением ubuntu. У вас есть коллега Вася, который хочет получить доступ к этому серверу. Он генерирует пару ssh ключей с помощью команды ssh-keygen и дает вам свой публичный ключ. В какой файл на сервере нужно записать ключ, чтобы Вася смог подключиться к терминалу сервера?
>  /root/.ssh/authorized_keys

- Тут вопрос про АПИ. Разберитесь, что такое long polling и webhooks, опишите сами в нескольких предложениях, как они работают.
>  Long Polling — это техника, при которой клиент отправляет запрос к серверу, и сервер держит соединение открытым до тех пор, пока не появится новая информация для отправки. После получения данных клиент сразу отправляет новый запрос, чтобы поддерживать постоянное соединение. Это позволяет получать обновления почти в реальном времени без частых запросов.
   Webhooks — это механизм, при котором сервер автоматически отправляет данные на указанный URL (например, на ваш сервер) при наступлении определённого события. В отличие от Long Polling, здесь инициатором передачи данных является сервер, а не клиент. Это удобно для получения мгновенных уведомлений о событиях. 

- Найдите информацию, что такое issues на гитхабе и для чего нужны. Также вставьте ссылки на пару примеров issues в популярных open source проектах. 
> Issues на GitHub — это инструмент для отслеживания задач, багов, улучшений и обсуждений в репозиториях. Они позволяют участникам проекта сообщать о проблемах, предлагать новые функции, задавать вопросы и координировать работу над проектом. Issues могут быть назначены на конкретных участников, помечены тегами (например, "bug", "enhancement"), объединены в milestones и связаны с pull requests.
   Примеры Issues в популярных open source проектах: React:https://github.com/facebook/react/issues/24513 
   VS Code:https://github.com/microsoft/vscode/issues/145200
  
- Ваш проект используется пустую папку images, но гит не поддерживает отслеживание пустых директорий. Что делать?
> Создать пустой файл внутри папки .gitkeep

# Mission 3
## Part0&1

[Link to video](https://drive.google.com/file/d/1wrG5qvFg4FLokW3TtUIpy7cojnObrKIX/view?usp=sharing)

## Part3

1.
~~~~sql
SELECT 
    username
FROM 
    users
~~~~
2.
~~~~sql
SELECT 
    from1,
    COUNT(*) AS message_count
FROM 
    messages
GROUP BY 
    from1
ORDER BY 
    message_count DESC;
~~~~
3.
~~~~sql
SELECT 
    to1 AS user_id,
    COUNT(*) AS received_message_count
FROM 
    messages
GROUP BY 
    to1
ORDER BY 
    received_message_count DESC
LIMIT 1;
~~~~
4.
~~~~sql
SELECT 
    AVG(message_count) AS avg_messages_per_user
FROM (
    SELECT 
        from1 AS user_id,
        COUNT(*) AS message_count
    FROM 
        messages
    GROUP BY 
        from1
) AS user_stats;
~~~~
