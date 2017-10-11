---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Audiomack API!

# User Download List

## Get All User Downloads

```shell
curl "https://api.audiomack.com/v1/user/downloads"
  -H "Authorization: meowmeowmeow"
```

> A valid response has the following code:

```http
HTTP/1.1 200 OK
```

> The above command returns JSON structured like this:

```json
["4","5","6","8"]
```

### HTTP Request

`GET https://api.audiomack.com/v1/user/downloads`

<aside class="notice">
  This is an authenticated call, so a valid access token and secret must be present
</aside>

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
type | all | What type of downloads to return.  Possible values are song, album or all.
exclude | | Comma-separated list of music ID's to exclude from the response.
offset | 0 | Which download to start with.
limit | 20 | Maximum number of downloads to return.

## Add downloads to the list

> A valid response has the following code:

```http
HTTP/1.1 201 Created
```

### HTTP Request

`POST https://api.audiomack.com/v1/user/downloads`

<aside class="notice">
  This is an authenticated call, so a valid access token and secret must be present
</aside>

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
music_id | | Either a single music ID, or a comma-separated list of music IDs that should be added to the user's download list

## Remove downloads from the list

> A valid response has the following code:

```http
HTTP/1.1 200 OK
```

### HTTP Request

`DELETE https://api.audiomack.com/v1/user/downloads/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | Either a single music ID, or a comma-separated list of music IDs that should be removed from the user's download list


