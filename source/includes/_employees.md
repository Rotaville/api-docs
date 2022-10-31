# Employees

Please see the following videos and documentation for more details on employee attributes.

Documentation: [Create a New Employee](https://rotaville.com/docs/new-rota)

Video: [Multiple Employees](https://rotaville.com/help/multiple-rotas)

Video: [Deactivate, Delete, and Disconnect Employees.](https://rotaville.com/help/deactivate-or-delete-or-disconnect-employee)


## Get All Employees


```shell
curl "http://rotaville.com/api4/owner/workforces/1/rotas" \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 45,
    "workplace_id": 1,
    "first_name": "Stephen",
    "last_name": "Slots",
    "email": "ss@examle.com"
    "is_manager": true,
    "active": true,
    ...
  },
  {
    "id": 45,
    "workplace_id": 1,
    "first_name": "David",
    "last_name": "Robson",
    "email": "david_r@examle.com"
    "is_manager": false,
    "active": true,
    ...
  },
  ...
]
```

This endpoint retrieves all employees for the given workplace.

### HTTP Request

`GET http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/employees`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employees


## Create a Employee

```shell
curl -X POST "http://example.com/api5/owner/workplaces/1/employees" \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"first_name":"Stephen",\
       "last_name": "Sloss",\
       "email": "ss@example.com",\
       "is_manager": true\
      }
```


> The above command returns JSON structured like this:

```json
{
  "id": 45,
  "workplace_id": 1,
  "first_name": "Stephen",
  "last_name": "Slots",
  "email": "ss@examle.com"
  "is_manager": true,
  "active": true,
  ...
}
```

This endpoint creates a specific employee.


### HTTP Request

`POST http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/employees`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee

### Body Parameters

Parameter | Description
--------- | -----------
first_name* | The first name of the employee
last_name* | The last name of the employee



## Get a Specific Employee

```shell
curl "http://example.com/api5/owner/workplaces/1/employees/45" \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 45,
  "workplace_id": 1,
  "first_name": "Stephen",
  "last_name": "Slots",
  "email": "ss@examle.com"
  "is_manager": true,
  "active": true,
  ....
}
```

This endpoint retrieves a specific employee.


### HTTP Request

`GET http://rotaville.com/api5/owner/workplaces/<WORKPLACE-ID>/employees/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
ID | The ID of the employee to retrieve

## Update a Employee

```shell
curl -X PATCH "http://example.com/api5/owner/workplaces/2/employees/123" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen" \
  -d '{"description":"RA qualified" }
```


> The above command returns JSON structured like this:

```json
{
  "id": 123,
  "workplace_id": 2,
  "first_name": "James",
  "last_name": "Smith",
  "desription": "RA qualified",
  "email": "js@examle.com"
  "active": true,
}
```

This endpoint can be used to update an employee


### HTTP Request

`PATCH http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/employees/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
ID | The ID of the employee to update

## Deactivate an Employee

A special update to an employee record is to *deactivate* them. 

You can do this by updating the `active` attribue to `false`.

## Invite an Employee

```shell
curl -X PUT "http://example.com/api5/owner/workplaces/2/employees/123/invite_or_connect" \
  -H 'Accept: application/json' \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 123,
  "workplace_id": 2,
  "first_name": "James",
  "last_name": "Smith",
  "email": "js@examle.com"
  "active": true,
  "invited_at":"2022-10-31T10:10:04",
  ...
}
```

This endpoint can be used to send an invitation to an employee.

Please see the following videos and documentation for more details on inviting and employee

Video: [Invite Users](https://rotaville.com/help/invite-users)

<aside class="notice">Please do not invite an employee before their own 
email address is fully configured and activated. 
Sending an invitation email to a not-yet-existing email-address will cause 
that email-adress to be automatically blocked from receiving further emails from us.
</aside>


### HTTP Request

`PUT http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/employees/<ID>/invite_or_connect`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
ID | The ID of the employee to invite


## Delete a Specific Employee

```shell
curl "http://rotaville.com/api5/owner/workplaces/3/employees/70" \
  -X DELETE \
  -H "Authorization: Bearer toKenTokenTOKen"
```


> The above command returns JSON structured like this:

```json
{
  "id": 70,
  "workplace_id": 3,
  "first_name": "James",
  "last_name": "Smith",
  "email": "js@examle.com"
  "active": true,
  ...
}
```

This endpoint deletes a specific employee.

### HTTP Request

`DELETE http://rotaville.com/api5/owner/workplace/<WORKPLACE-ID>/employees/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
WORKPLACE-ID | The ID of the workplace for the employee
ID | The ID of the workplace to delete

<aside class="warning">WARNING: Deleting an employee is PERMANENT. 
There is no <em>undo</em>. All employee notes and shift assignments (historical and future), 
for the employee will also be deleted.
<br>
It is recommended that an employee be <strong>DEACTIVATED</strong> instead of being deleted.
</aside>

