---
layout: default
---

<div id="head">
  <div id="main_title">AImager</div>
</div>

<div>
{% assign moviecase =  site.posts | group_by: "casename" | sort: "name" %}
{% for item in moviecase %}
  <p><a href="/{{ item.items[0].douban_id }}.html" class="moviecase">{{ item.name }}</a></p>

  <div class="home_tag_div">
  {% for tag in site.tags %}
  {% assign index = 0 %}
  {% for post in tag[1] %}
  {% if post.casename == item.name and index == 0 %}
  {% assign index = 1 %}
  <span class="home_tag">{{ tag[0] }}</span>
  {% endif %}
  {% endfor %}
  {% endfor %}

  </div>
{% endfor %}
</div>
