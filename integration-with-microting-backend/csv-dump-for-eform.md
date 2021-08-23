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
{% api-method-parameter name="includeCheckListText" type="boolean" required=false %}
Wheter the headers should include the containing checklist text
{% endapi-method-parameter %}

{% api-method-parameter name="gpsCoordinates" type="boolean" required=false %}
Whether the GPS coordinates should be included in the image urls
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="number" required=true %}
ID of the eForm you want to get a CSV dump for
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="string" required=false %}
DateTime for start of period
{% endapi-method-parameter %}

{% api-method-parameter name="end" type="number" required=false %}
DateTime for end of period
{% endapi-method-parameter %}

{% api-method-parameter name="utcTime" type="boolean" %}
Whether the time should be in local time or UTC
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



