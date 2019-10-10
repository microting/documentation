# Outer resources

{% api-method method="get" host="http://localhost:5000" path="/api/outer-inner-resource-pn/outer-resources" %}
{% api-method-summary %}
Get all outer resources
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

{% api-method-query-parameters %}
{% api-method-parameter name="Sort" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="PageIndex" type="integer" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="Offset" type="integer" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="IsSortDsc" type="boolean" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="PageSize" type="integer" required=false %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
	"model": {
		"total": 2,
		"outerResourceList": [{
				"id": 2,
				"name": "Outer resource 1",
				"relatedInnerResourcesIds": null
			},
			{
				"id": 3,
				"name": "Outer resource 2",
				"relatedInnerResourcesIds": null
			}
		],
		"name": "Outer resources"
	},
	"success": true,
	"message": "Success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


