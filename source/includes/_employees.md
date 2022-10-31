# Employees

<aside class="notice">
At the API level, A Rotaville Workforce is known as a <code>workplace</code>.
This might change in a future version of the API. 
</aside>

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

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

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
  "business_hours_finish": 36
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

This endpoint deletes a specific workplace.

### HTTP Request

`DELETE http://rotaville.com/api5/owner/workplace/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the workplace to delete

<aside class="warning">Only workplaces "owned" by the api user can be deleted.</aside>

