# Resource time registrations

{% api-method method="get" host="http://localhost:5000" path="/api/outer-inner-resource-pn/resource-time-registrations/{lastRegistrationId}" %}
{% api-method-summary %}
Get time registrations
{% endapi-method-summary %}

{% api-method-description %}
This endpoint will return up to 10 time registrations at a time.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="lastRegistrationId" type="string" required=true %}
ID of the last registration you pulled, starts from 0
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer access\_token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
	"model": {
		"resourceTimeRegistrationModels": [{
			"id": 1,
			"doneAt": "2019-10-11T08:54:57.050Z",
			"outerResourceName": "Outer resource 1",
			"outerResourceId": 1,
			"innerResourceName": "Inner resource 1",
			"innerResourceId": 10,
			"timeInSeconds": 4242,
			"doneByDeviceUserId": 1,
			"doneByDeviceUserName": "John Doe",
			"sdkCaseId": 3223
		}],
		"lastResourceTimeRegistrationId": 1
	},
	"success": true,
	"message": "string"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



