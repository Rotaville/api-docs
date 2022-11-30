# Employee Photo (Avatar)

<aside class="notice">
At the API level, An Employee Photo is known as a <code>employee avatar</code>.
This might change in a future version of the API. 
</aside>


## Get Workplace Avatar


```shell
curl "http://rotaville.com/api4/owner/workforces/1/employees/5/avatar" \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
{
    "avatar_id": 3,
    "pic_id": 4,
    "cpt": {
        "base": "#337D89",
        "base2": "#6D8288"
    }
}
```

This endpoint returns the avatar fields of the corresponding parent employee. When no avatar exists a 404 status wil be returned.

### HTTP Request

`GET http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/employees/<EMPLOYEE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
EMPLOYEE-ID | The ID of the employee for the avatar


## Create Employee Avatar

```shell
curl -X POST "http://rotaville.com/api5/owner/workplaces/1/employees/8/avatar" \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"data64":"`base64 -i face.jpg`"}'
```


> The above command returns JSON structured like this:

```json
{
    "avatar_id": 6,
    "pic_id": 6,
    "cpt": {
        "base": "#337D89",
        "base2": "#6D8288"
    }
}
```

This endpoint creates(uploads) a new employee avatar. 
The returned json data should be merged into parent employee record.

### HTTP Request

`POST http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/employees/<EMPLOYEE-ID> avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
EMPLOYEE-ID | The ID of the employee for the avatar

### Body Parameters

Parameter | Description
--------- | -----------
data64*   | The image file (jpg or png) base64 encoded


## Update Employee Avatar

```shell
curl -X PATCH "http://rotaville.com/api5/owner/workplaces/2/employees/5/avatar" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"data64":"`base64 -i smiling.jpg`"}'

```


> The above command returns JSON structured like this:

```json
{
    "avatar_id": 8,
    "pic_id": 8,
    "cpt": {
        "base": "#237D89",
        "base2": "#9D8288"
    }
}
```

This endpoint can be used to update/replace an employee avatar
The returned json data should be merged into parent employee record.


### HTTP Request

`PATCH http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/employees/<EMPLOYEE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
EMPLOYEE-ID | The ID of the employee for the avatar

### Body Parameters

Parameter | Description
--------- | -----------
data64*   | The image file (jpg or png) base64 encoded


## Delete Employee Avatar

```shell
curl "http://rotaville.com/api5/owner/workplaces/2/employees/9/avatar" \
  -X DELETE \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
{
    "avatar_id": null,
    "pic_id": 7,
    "cpt": {
        "base": "#347D89",
        "base2": "#A98288"
    }
}
```

This endpoint deletes the employee avatar. 
The returned json should be merged into the parent employee record.

### HTTP Request

`DELETE http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/employees/<EMPLOYEE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
EMPLOYEE-ID | The ID of the employee for the avatar


