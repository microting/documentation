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

{% api-method method="post" host="http://localhost:5000" path="/api/outer-inner-resource-pn/outer-resources" %}
{% api-method-summary %}
Create a new outer resource
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
{% api-method-parameter name="name" type="string" required=true %}
Name of the outer resource
{% endapi-method-parameter %}

{% api-method-parameter name="relatedInnerResourceIds" type="array" required=true %}
List of inner resource ids or null
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
	"success": true,
	"message": "Outer resource created successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="http://localhost:5000" path="/api/outer-inner-resource-pn/outer-resources" %}
{% api-method-summary %}
Update an outer resource
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
{% api-method-parameter name="name" type="string" required=true %}
Name of outer resource
{% endapi-method-parameter %}

{% api-method-parameter name="relatedInnerResourceIds" type="array" required=true %}
List of inner resource ids or null
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
	"message": "Outer resource updated successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="http://localhost:5000" path="/api/outer-inner-resource-pn/outer-resources" %}
{% api-method-summary %}
Delete an outer resource
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
Id of the outer resource to delete
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
	"message": "Outer resource deleted successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

