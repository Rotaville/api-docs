# Rotas

Please see the following videos and documentation for more details on rota attributes.

Documentation: [Create a New Rota](https://rotaville.com/docs/new-rota)

Video: [Multiple Rotas](https://rotaville.com/help/multiple-rotas)


## Get All Rotas


```shell
curl "http://rotaville.com/api4/owner/workforces/1/rotas" \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 10,
    "name": "On Site",
    "description": "our work rota",
    "workplace_id": 1
  },
  {
    "id": 15,
    "name": "On Call",
    "workplace_id": 1
  }
]
```

This endpoint retrieves all rotas for the given workplace.

### HTTP Request

`GET http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/rotas`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the rotas


## Create a Rota

```shell
curl -X POST "http://example.com/api5/owner/workplaces/1/rotas" \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"name":"Holidays",\
       "description": "Holidays and Sick Leave"}
```


> The above command returns JSON structured like this:

```json
{
  "id": 10,
  "workplace_id": 1,
  "name": "Holidays",
  "description": "Holidays and Sick Leave"
}
```

This endpoint creates a specific rota.


### HTTP Request

`POST http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/rotas`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the rota

### Body Parameters

Parameter | Description
--------- | -----------
name* | The name of the rota


## Get a Specific Rota

```shell
curl "http://example.com/api5/owner/workplaces/1/rotas/45" \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 45,
  "name": "KeepGoing",
  "description": "our work rota",
  "workplace_id": 1
}
```

This endpoint retrieves a specific rota.


### HTTP Request

`GET http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/rotas/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the rota
ID | The ID of the rota to retrieve

## Update a Rota

```shell
curl -X PATCH "http://example.com/api5/owner/workplaces/2/rotas/123" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"description":"Attention to Detail" }
```


> The above command returns JSON structured like this:

```json
{
  "id": 123,
  "name": "Our Rota",
  "description": "Attention to Detail"
  "workplace_id": 2,
}
```

This endpoint can be used to update a rota


### HTTP Request

`PATCH http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/rotas/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the rota
ID | The ID of the rota to update


## Delete a Specific Rota

```shell
curl "http://rotaville.com/api5/owner/workplaces/2/rotas/99" \
  -X DELETE \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 99,
  "name": "Unused Rota",
  "description": "It's okay to delete me after Jan 1st 2024"
  "workplace_id": 2,
}
```

This endpoint deletes a specific workplace.

### HTTP Request

`DELETE http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/rotas/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the rota
ID | The ID of the workplace to delete

<aside class="warning">WARNING: Deleting a rota is PERMANENT. 
There is no <em>undo</em>. All shifts (historical and future), 
and all shift assignments, on the rota will also be deleted.</aside>

