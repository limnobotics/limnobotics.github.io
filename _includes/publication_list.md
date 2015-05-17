{% for item in include.list %}
{% assign link = item.link | strip_newlines %}
{% assign linktemp = link | truncate: 4, '' %}
{% if linktemp == "http" %}
{{ item.text | strip_newlines }}{% include extlink.md link=link %}
{% elsif link == '' %}
{{ item.text | strip_newlines }}
{% else %}
{{ item.text | strip_newlines }}{% include pdflink.md filename=link %}
{% endif %}
{% endfor %}

