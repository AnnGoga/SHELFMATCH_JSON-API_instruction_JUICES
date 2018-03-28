# SHELFMATCH_JSON-API_instruction_JUICES

## Для детектирования и классификации товаров на изображении через веб-интерфейс отправьте POST-запрос с изображением в формате base64 на URL:
http://api-juices.shelfmatch.com/session

## Описание запроса:
1. POST запрос: /session
2. Заголовки:

2.1. Accept: application/json;charset=UTF-8

2.2. Content-Type: application/json

3. Тело запроса:
4. Пример запроса:
5. Пример удачного ответа:

## Для получения спиcка торговых точек в системе отправьте GET-запрос с на URL:

## Для получения ответа по идентификатору сессии необходимо отправить GET-запрос на URL:
http://api-juices.shelfmatch.com/session

## Описание запроса:
1. GET запрос: /session?sessionId=\<session id\>
2. Параметр запроса в строке URL: session id – идентификатор сессии
3. Пример URL запроса:
http://api-juices.shelfmatch.com/session?sessionId=6bfb962c-d67b-4dc2-9468-8be11559134f 
  
4. Тело ответа:
5. Пример удачного ответа:
