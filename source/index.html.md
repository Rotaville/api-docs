---
title: Rotaville API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - owner
  - workplaces
  - rotas
  - employees
  - errors

search: true

code_clipboard: true

meta:
  - name: description
  - content: Documentation for the Rotaville API

---

# Introduction

Welcome to the Rotaville API! You can use our API to access Rotaville API endpoints, which can get information your various workforces, rotas, and employees in your account.

We have language bindings in Shell! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This API documentation page was created with [Slate](https://github.com/slatedocs/slate).

# Restful JSON Api

Most requests to, and responses from, the API are in JSON format. 

## Request Headers

HTTP requests should include the header 

`Accept: application/json`

(or append the `.json` extenstion to the request URL).

## Data format

Data included with HTTP requests should be encoded in JSON 
format and the header 

`Content-Type: application/json`

included with the request.



# Authentication

> To authorize, first request a session token using your API key:

```shell
# With shell, you can just pass the correct header with each request
curl "https://rotaville.com/api5/session" \
  -H 'Content-Type: application/json'
  -d '{"email":"my@email.address","api_key":"API_KEY"}'
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "token": "toKenTokenTOKen"
}
```

> where `toKenTokenTOKen` is your session token.

> Subsequent requests to the API can use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: Bearer toKenTokenTOKen"
```

> Make sure to replace `toKenTokenTOKen` with your session token.

To use the Rotaville API you need API KEY. You can request access to the Rotaville API and API KEY by contacting Rotaville Support.

The API KEY can be used request a new session TOKEN.

After some period of time the session token will expire and a new token will be required.

Rotaville expects for the TOKEN to be included in all subsequent API requests to the server in a header that looks like the following:

`Authorization: Bearer toKenTokenTOKen`

<aside class="notice">
You must replace <code>toKenTokenTOKen</code> with your session token.
</aside>

