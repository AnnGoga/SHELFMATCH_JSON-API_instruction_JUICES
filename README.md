# SHELFMATCH_JSON-API_instruction_JUICES

### Для детектирования и классификации товаров на изображении через веб-интерфейс отправьте POST-запрос с изображением в формате base64 на URL:
http://api-juices.shelfmatch.com/session

## Описание запроса:
1. POST запрос: /session
2. Заголовки:  
2.1. Accept: application/json;charset=UTF-8  
2.2. Content-Type: application/json  

3. Тело запроса:
4. Пример запроса:
5. Пример удачного ответа:

### Для получения спиcка торговых точек в системе отправьте GET-запрос на URL:

http://api-juices.shelfmatch.com/tradepoints

## Описание запроса:
1. GET запрос: /tradepoints?sessionId=\<session id\>  
2. Параметр запроса в строке URL: **session id** – идентификатор сессии  
3. Пример URL запроса:  
http://api-juices.shelfmatch.com/tradepoints?sessionId=6bfb962c-d67b-4dc2-9468-8be11559134f   
4. Тело ответа:  
- **tradePoints** - торговые точки, набор результатов:  
    - **city** - населенный пункт;  
    - **address** - адрес;  
    - **id** - идентификационный номер;  
    - **country** - страна;  
- **status** - статус сессии;    

5. Пример удачного ответа:  
```
{
"tradePoints": [ {
    "city":null,
    "address":"trade point 1",
    "id":"01",
    "country":null
}],
"status":"ok"
}
```
### Для получения ответа по идентификатору сессии необходимо отправить GET-запрос на URL:  
http://api-juices.shelfmatch.com/session

## Описание запроса:
1. GET запрос: /session?sessionId=\<session id\>
2. Параметр запроса в строке URL: **session id** – идентификатор сессии
3. Пример URL запроса:  
http://api-juices.shelfmatch.com/session?sessionId=6bfb962c-d67b-4dc2-9468-8be11559134f  
4. Тело ответа:  
- **session** - ответ по запросу:  
    - **processed** - сессия обработана (1) или нет (0);  
    - **totalImagePath** - полное изображение для распознавания;  
    - **foundObjects** - набор результатов:  
        - **width** - ширина;  
        - **height** - высота;  
        - **x** - ордината левого верхнего угла;  
        - **y** - абсцисса левого верхнего угла;  
        - **score** - вероятность точности распознавания SKU на полке на данном изображении;  
        - **label** - наименование SKU;  
        - **positionId** - позиция SKU на полке;  
        - **sessionId** - идентификатор сессии;  
        - **id** - порядковый номер SKU;  
        - **number** - номер полки.   
    - **verticalLayout** - склейка нескольких картинок по вертикали (true) или горизонтали (false);  
    - **tradePointId** - номер торговой точки из базы данных;
    - **created** - дата создания сессии в формате long;  
    - **accoutnId** - идентификационный номер аккаунта.  
    - **imageParts** - склееное изображение:  
    - **detectionTime** - время распознавания;  
    - **id(path)** - идентификационный номер параметра path;  
    - **path** - область в imageParts;  
- **status** - статус сессии.  
   
5. Пример удачного ответа:  
```
{  
"session": {  
    "processed":1,  
    "totalImagePath":"/6bfb962c-d67b-4dc2-9468-8be11559134f/full_image.jpg",  
    "foundObjects": [{  
        "width":79,  
        "height":244,  
        "x":1323,  
        "y":116,  
        "score":0.9998941421508789,  
        "label":"rich_orange_mango_1l_solid",  
        "positionId":null,  
        "sessionId":"6bfb962c-d67b-4dc2-9468-8be11559134f",  
        "id":2783386,  
        "number":0  
},  
{  
        "width":77,  
        "height":226,  
        "x":1142,  
        "y":405,  
        "score":0.9996134638786316,  
        "label":"rich_multi_1l_solid",  
        "positionId":null,  
        "sessionId":"6bfb962c-d67b-4dc2-9468-8be11559134f",  
        "id":2783400,  
        "number":0  
}],  
"verticalLayout":false,  
    "tradePointId":"01",  
    "created":1509102006000,  
    "accoutnId":49,  
"imageParts": [{  
    "detectionTime":1054,  
    "sessionId":"6bfb962c-d67b-4dc2-9468-8be11559134f",  
    "id":2218,  
    "path":"/6bfb962c-d67b-4dc2-9468-8be11559134f/1.jpg"  
}],  
    "detectionTime":1054,  
    "id":"6bfb962c-d67b-4dc2-9468-8be11559134f"  
},  
"status":"ok"  
}
```  
