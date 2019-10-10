# Device users

{% api-method method="get" host="http://localhost:5000" path="/api/device-users/index" %}
{% api-method-summary %}
Get list of devices users
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get a list of all current device users.  
In the example below we assume we have two device users; a 1 and a 2:
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
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
	"model": [{
		"siteId": 187924,
		"siteName": "a 1",
		"firstName": "a",
		"lastName": "1",
		"customerNo": 342345,
		"otpCode": 950286,
		"unitId": 185092,
		"workerUid": 161047
	}, {
		"siteId": 165341,
		"siteName": "a 2",
		"firstName": "a",
		"lastName": "2",
		"customerNo": 342345,
		"otpCode": 193498,
		"unitId": 129455,
		"workerUid": 923185
	}],
	"success": true,
	"message": "Success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="http://locahost:5000" path="/api/device-users/create" %}
{% api-method-summary %}
Create a new device user
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer access\_token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="userFirstName" type="string" required=true %}
First name of the user to create, eg: John
{% endapi-method-parameter %}

{% api-method-parameter name="userLastName" type="string" required=true %}
Last name of the user to create, eg: Doe
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
	"success": true,
	"message": "Device user \"John Doe\" was created successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://locahost:5000" path="/api/device-users/update" %}
{% api-method-summary %}
Update a device user
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer access\_token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="number" required=true %}
Id of the user to update \(siteId from the index\)
{% endapi-method-parameter %}

{% api-method-parameter name="userFirstName" type="string" required=true %}
First name of the user to update, eg: John
{% endapi-method-parameter %}

{% api-method-parameter name="userLastName" type="string" required=true %}
Last name of the user to update, eg: Doe
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
	"success": true,
	"message": "Device user updated successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="http://locahost:5000" path="/api/device-users/delete" %}
{% api-method-summary %}
Delete a device user
{% endapi-method-summary %}

{% api-method-description %}
id is the siteId from the index response
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
siteId of the device user to delete
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

{% endapi-method-response-example-description %}

```javascript
{
	"success": true,
	"message": "Device user \"John Doe\" deleted successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

