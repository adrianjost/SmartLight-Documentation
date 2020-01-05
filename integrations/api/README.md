# API

{% hint style="danger" %}
The API is currently WIP and under active development. You can follow the implementation here: [https://github.com/adrianjost/SmartLight-IFTTT-Google-Home-Adapter/issues/8](https://github.com/adrianjost/SmartLight-IFTTT-Google-Home-Adapter/issues/8)
{% endhint %}

## /units

{% api-method method="get" host="" path="/units" %}
{% api-method-summary %}
List All Units
{% endapi-method-summary %}

{% api-method-description %}
This lists all units of the given user
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="authorization-token" type="string" required=true %}
the api token the user can generate in the frontend
{% endapi-method-parameter %}

{% api-method-parameter name="authorization-userid" type="string" required=true %}
the userid the user can find in the frontend
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns a JSON Object with the status code and the data or an error description
{% endapi-method-response-example-description %}

```
{
    "status": 200,
    "data": [
        {
            "state": {
                "gradient": false,
                "color": "#ff00ff"
            },
            "name": "Bett",
            "id": "someId",
            "tags": ["a Tag"],
            "created_at": {
                "_seconds": 1578148014,
                "_nanoseconds": 796000000
            },
            "updated_at": {
                "_seconds": 1578148482,
                "_nanoseconds": 521000000
            },
            "ip": "192.168.1.233",
            "channelMap": {
                "b": 1,
                "r": 2,
                "g": 3
            },
            "updated_by": "userId",
            "type": "LAMP", // or GROUP
            "icon": "some-icon",
            "lamptype": "RGB", // or WWCW
            "created_by": "userId",
            "hostname": "some-hostname"
        }
        // ...
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": 404,
    "error": "unit not found"

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/unit/:id" %}
{% api-method-summary %}
Get Unit Details
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="authorization-token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="authorization-userid" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": 200,
    "data": {
        "state": {
            "gradient": false,
            "color": "#ff00ff"
        },
        "name": "Bett",
        "id": "someId",
        "tags": ["a Tag"],
        "created_at": {
            "_seconds": 1578148014,
            "_nanoseconds": 796000000
        },
        "updated_at": {
            "_seconds": 1578148482,
            "_nanoseconds": 521000000
        },
        "ip": "192.168.1.233",
        "channelMap": {
            "b": 1,
            "r": 2,
            "g": 3
        },
        "updated_by": "userId",
        "type": "LAMP", // or GROUP
        "icon": "some-icon",
        "lamptype": "RGB", // or WWCW
        "created_by": "userId",
        "hostname": "some-hostname"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="" path="/units/:id" %}
{% api-method-summary %}
Update Unit \(State\)
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="authorization-token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="authorization-userid" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="token" type="string" required=false %}
Can be used 
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=false %}
of the header field
{% endapi-method-parameter %}

{% api-method-parameter name="userid" type="string" required=false %}
Can be used instead of the header field
{% endapi-method-parameter %}

{% api-method-parameter name="payload" type="object" required=true %}
the new unit, also can be incomplete. The payload will be merged with the existing entry.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": 200,
    "data": {
        // the new unit object
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="" path="/units/:id" %}
{% api-method-summary %}
Delete a Unit
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="authorization-userid" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="authorization-token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": 200
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

