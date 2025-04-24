---
layout: single
title: "往年活动"
permalink: /contents/
excerpt: ""
header:
  overlay_image: /assets/images/banner.jpg
  overlay_filter: rgba(0, 0, 0, 0.1)
---

{% for content in site.data.contents %}

  <h3>{{ content.year }}</h3>
  <p class="speaker-affiliation">地点：{{ content.place }}</p>
  <p class="speaker-affiliation">网站：
    <a href="{{ content.link }}" target="_blank">{{ content.link }}</a>
  </p>
{% endfor %}
