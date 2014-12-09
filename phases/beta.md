---
layout: default
title: Beta
---

# Beta

{% for topic in site.data.beta %}
{% assign topic_name = topic[0] %}
{% assign points = topic[1] %}

## {{ topic_name }}

{% for data in points %}
{% assign point = data[0] %}
{% assign info = data[1] %}
<hr>
<!-- <div>
<input type="submit" id="show" value="Show info">
<input type="submit" id="hide" value="Hide info">
</div>
 -->
{% if point == "group"%}
{% for group_point in info.points %}
{% assign sub_point = group_point[0] %}
{% assign sub_criteria = group_point[1] %}
### <a href="https://www.gov.uk/service-manual/digital-by-default#criterion-{{ sub_point }}" id="point-{{ sub_point }}">DBD point {{ sub_point }}</a>

#### Criteria
*{{ sub_criteria }}*


{% endfor %}

{% else %}
### <a href="https://www.gov.uk/service-manual/digital-by-default#criterion-{{ point }}" id="point-{{ point }}">DBD point {{ point }}</a>

#### Criteria
*{{ info.criteria }}*

{% endif %}

#### Prompts
{{ info.prompts }}

#### Evidence
{{ info.evidence }}

{% endfor %}

{% endfor %}