---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Flow Sensors

## Get All Flow Sensors

```shell
curl "https://app.flowcommand.com/api/v1/flow_sensors/"
  -H "Authorization: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
	"count": 2,
	"next": null,
	"previous": null,
	"results": [{
		"id": 1,
		"name": "Sensor 1",
		"latitude": 29.760435,
		"longitude": -95.3698,
		"pipe_diameter": 14.64,
		"last_ping_flowrate": 5356.92,
		"last_ping_datetime": "2019-02-05T20:41:02+00:00"
	}, {
		"id": 2,
		"name": "Sensor 2",
		"latitude": 29.760435,
		"longitude": -95.3698,
		"pipe_diameter": 19.14,
		"last_ping_flowrate": 0,
		"last_ping_datetime": "2019-02-05T20:15:08+00:00"
	}]
}
```

This endpoint retrieves all sensors.

### HTTP Request

`GET https://app.flowcommand.com/api/v1/flow_sensors/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Page (each page contains 1000 items)

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get Pings for a Specific Flow Sensor

```shell
curl "https://app.flowcommand.com/api/v1/flow_sensors/1/pings/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
	"count": 2,
	"next": null,
	"previous": null,
	"results": [{
		"id": 1,
		"sensor_id": 1,
		"sensor_name": "Sensor 1",
		"flowrate": 759.99,
		"datetime": "2019-02-05T20:15:08+00:00"
	}, {
		"id": 2,
		"sensor_id": 1,
		"sensor_name": "Sensor 1",
		"flowrate": 0.0,
		"datetime": "2019-02-05T19:44:09+00:00"
	}]
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://app.flowcommand.com/api/v1/flow_sensors/<FLOW_SENSOR_ID>/pings/`

### URL Parameters

Parameter | Description
--------- | -----------
page | 1 | Page (each page contains 1000 items)

