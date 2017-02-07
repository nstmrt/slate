# Жалобы на товар

## Получение списка стандартных жалоб

```shell
curl "https://api.instamart.ru/v2/flags"
```
> Эта комманда возвращает следующий JSON:

```json
[
  {
    "id": 1,
    "name": "Неверное описание"
  }
]
```

<aside class="warning">
  not implemented
</aside>

Стандартный список ошибок можно загрузить, выполнив запрос:

`GET https://api.instamart.ru/v2/flags`

## Отправка жалобы

> Пример отправки стандартной жалобы из списка:

```shell
curl "https://api.instamart.ru/v2/products/1/flags" \
  -H "Authorization: Token token=<% TOKEN %>" \
  -X POST \
  -d product_flag[flag_id]=1
```

> Пример отправки собственной жалобы

```shell
curl "https://api.instamart.ru/v2/products/#{PRODUCT_ID}/flags" \
  -H "Authorization: Token token=<% TOKEN %>" \
  -X POST \
  -d "product_flag[description]=Слишком высокая цена"
```

<aside class="warning">
  not implemented
</aside>

Чтобы отправить жалобу на товар, выполните следующий запрос, указав `id` жалобы:

`POST https://api.instamart.ru/v2/products/#{PRODUCT_ID}/flags`

Также, используя этот же URL, можно отправить свой текст жалобы, указав его в параметре `description`

### Параметры запроса

Параметр | Обязательный | Описание
--------- | ------- | -----------
product_id | Да | id продукта
product_flag[flag_id] | Да (если не указан `description`) | id жалобы 
product_falg[description] | Да (если не указан `flag_id`) | текст жалобы