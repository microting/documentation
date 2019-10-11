# Association of device users

{% api-method method="get" host="http://localhost:5000" path="/api/outer-inner-resource-pn/settings/sites" %}
{% api-method-summary %}
Get devices users associated
{% endapi-method-summary %}

{% api-method-description %}
Get a list of device users associated with the plugin. Each number in the model list represent a device user \(siteId\). See Device Users on how to get a list.
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
	"model": [
		4,
		5
	],
	"success": true,
	"message": "Success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://localhost:5000" path="/api/outer-inner-resource-pn/settings/sites" %}
{% api-method-summary %}
Set device users associated
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="siteIds" type="array" required=false %}
A list of siteIds, each representing a Device user
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
	"message": "Success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

