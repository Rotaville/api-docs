# Workforce Logo (Avatar)

<aside class="notice">
At the API level, A Workforce Logo is known as a <code>workplace avatar</code>.
This might change in a future version of the API. 
</aside>

Please see the following videos and documentation for more details on workplace attributes.

Documentation: [Upload Workforce Logo](https://rotaville.com/docs/workforce-logo)


## Get Workplace Avatar


```shell
curl "http://rotaville.com/api4/owner/workforces/1/avatar" \
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

This endpoint returns the avatar fields of the corresponding parent workplace. When no avatar exists a 404 status wil be returned.

### HTTP Request

`GET http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the avatar


## Create Workplace Avatar

```shell
curl -X POST "http://rotaville.com/api5/owner/workplaces/1/avatar" \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"data64":"`base64 -i logo.png`"}'
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

This endpoint creates(uploads) a new workplace avatar. 
The returned json data should be merged into parent workplace record.

### HTTP Request

`POST http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the avatar

### Body Parameters

Parameter | Description
--------- | -----------
data64*   | The image file (jpg or png) base64 encoded


## Update Workplace Avatar

```shell
curl -X PATCH "http://example.com/api5/owner/workplaces/2/avatar" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"data64":"`base64 -i new_logo.jpg`"}'

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

This endpoint can be used to update/replace a workplace avatar
The returned json data should be merged into parent workplace record.


### HTTP Request

`PATCH http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the avatar

### Body Parameters

Parameter | Description
--------- | -----------
data64*   | The image file (jpg or png) base64 encoded


## Delete Workplace Avatar

```shell
curl "http://rotaville.com/api5/owner/workplaces/2/avatar" \
  -X DELETE \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
{
    "avatar_id": null,
    "pic_id": 2,
    "cpt": {
        "base": "#147D89",
        "base2": "#998288"
    }
}
```

This endpoint deletes the workplace avatar. 
The returned json should be merged into the parent workplace record.

### HTTP Request

`DELETE http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace with the avatar to delete


