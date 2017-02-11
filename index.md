---
layout: default
---

{% assign pagesize = 0 %}
{% for file in site.static_files %}
   {% if file.path contains 'main.html' %}
		{% assign pagesize = pagesize | plus: 1 %}
   {% endif %}
{% endfor %}

<script>
	var timestamp = Date.parse(new Date());
	timestamp = timestamp / 1000;
	window.location.href="/v"+timestamp%{{ pagesize }}+"/html/main.html";
</script>
