# CSV dump for eForm

{% api-method method="get" host="http://locahost:5000" path="/api/template-files/csv/{id}" %}
{% api-method-summary %}
Get CSV file
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get a CSV dump of all data collected on a specific eForm.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=false %}
ID of the eForm you want to get a CSV dump for
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

```
CSV file
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



