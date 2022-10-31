# Workforces - AKA Workplaces

<aside class="notice">
At the API level, A Rotaville Workforce is known as a <code>workplace</code>.
This might change in a future version of the API. 
</aside>

Please see the following videos and documentation for more details on workplace attributes.

Documentation: [Workforce Settings](https://rotaville.com/docs/workforce-settings)

Video: [Advanced Workforce Settings](https://rotaville.com/help/advanced-workforce-settings)


## Get All Workplaces


```shell
curl "http://rotaville.com/api4/owner/workforces" \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "user_id": 1,
    "name": "Fluffums",
    "description": "calico",
    "business_hours_start": 6,
    "business_hours_finish": 20
    ...
  },
  {
    "id": 2,
    "user_id": 1,
    "name": "Maximum Hours",
    "description": "just another job",
    "business_hours_start": 7,
    "business_hours_finish": 36
    ...
  }
]
```

This endpoint retrieves all workplaces in which the owner is a manager.

### HTTP Request

`GET http://rotaville.com/api5/owner/workplaces`


## Create a Workplace

```shell
curl -X POST "http://example.com/api5/owner/workplaces" \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"name":"Family Care Inc.",\
       "default_rota_name":"On Site",\
       "skip_example_employees": true,\
       "skip_example_shifts": true}
```


> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "user_id": 1,
  "name": "Family Care Inc."
  "business_hours_start": 6,
  "business_hours_finish": 23,
  ...
}
```

This endpoint retrieves a specific workforce.


### HTTP Request

`POST http://rotaville.com/api5/owner/workplaces`

### Body Parameters

Parameter | Description
--------- | -----------
name* | The name of the workplace

### Special Body Parameters

Parameter | Type | Description
--------- | ---- | -----------
default_rota_name | String | A name for the default rota created for a new workplace
default_rota_description | String | A description for the default rota created for a new workplace
skip_example_employees | Boolean | set `true` to avoid example employees being created
skip_example_shifts | Boolean | set `true` to avoid example shifts being added

## Get a Specific Workplace

```shell
curl "http://example.com/api5/owner/workplaces/2" \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "user_id": 1,
  "name": "Maximum Hours",
  "description": "just another job",
  "business_hours_start": 7,
  "business_hours_finish": 36,
  ...
}
```

This endpoint retrieves a specific workforce.


### HTTP Request

`GET http://rotaville.com/api5/owner/workplaces/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the workplace to retrieve

## Update a Workplace

```shell
curl -X PATCH "http://example.com/api5/owner/workplaces/2" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"business_hours_start": 9, "business_hours_finish": 17 }
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "user_id": 1,
  "name": "Maximum Hours",
  "description": "just another job",
  "business_hours_start": 9,
  "business_hours_finish": 17,
  ...
}
```

This endpoint can be used to update a workplace


### HTTP Request

`PATCH http://rotaville.com/api5/owner/workplace/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the workplace to update




## Delete a Specific Workplace

```shell
curl "http://rotaville.com/api5/owner/workplaces/2" \
  -X DELETE \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "user_id": 1,
  "name": "Maximum Hours",
  "description": "just another job",
  "business_hours_start": 7,
  "business_hours_finish": 36
  ...
}
```

<aside class="success">Workplace deletion is currently disabled in the API. Please use the UI.</aside>

This endpoint deletes a specific workplace.

### HTTP Request

`DELETE http://rotaville.com/api5/owner/workplace/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the workplace to delete

<aside class="warning">Only workplaces "owned" by the api user can be deleted.</aside>

<aside class="warning">WARNING: Deleting a workplace is PERMANENT. 
There is no <em>undo</em>. All employees, all rotas, and all shifts (historical and future), 
in the workplace will be permanently deleted.</aside>


