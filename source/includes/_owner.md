# Owner (API User)

<aside class="notice">
At the API level, the "owner" is the database record of the API User.
</aside>

Attributes of the owner correlate to Rotaville *User Profile* and Rotaville *User Settings*.

Please see the following videos and documentation for more details on these attributes.

[User Profile](https://rotaville.com/help/user-profile)

[User Settings](https://rotaville.com/help/user-settings)

<aside class="notice">
A typical API integration will probably not need to use or update the owner record. 
Updates to these settings are normally infrequent and are best done throught Rotaville UI.
</aside>



## Get Owner


```shell
curl "http://rotaville.com/api4/owner" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "login": "Jason",
    "first_name": "Jason",
    "last_name": "Lee",
    "email": "jason@example.com",
    "twelve_hour_time": true,
    ...
}
```

This endpoint retrieves the owner (api user)

### HTTP Request

`GET http://rotaville.com/api5/owner`


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Update Owner

```shell
curl -X PATCH "http://example.com/api5/owner" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen"
  -d '{"twelve_hour_time": false}'
```


> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "login": "Jason",
    "first_name": "Jason",
    "last_name": "Lee",
    "email": "jason@example.com",
    "twelve_hour_time": false,
    ...
}
```

This endpoint can be used to update the owner (API User)


### HTTP Request

`PATCH http://rotaville.com/api5/owner`


