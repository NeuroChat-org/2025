---
layout: single
title: "会议日程"
permalink: /program/
header:
  overlay_image: /assets/images/banner.jpg
  overlay_filter: rgba(0, 0, 0, 0.1) # 半透明遮罩
  # caption: "Photo by [NASA](https://unsplash.com)"
---

{% for day in site.data.schedule %}

<h2>第 {{ day.day }} 天 - {{ day.date | date: "%Y年%m月%d日" }}</h2>
<table>
  {% for event in day.events %}
  <tr>
    <td>{{ event.time }}</td>
    <td>{{ event.title }}</td>
    <td>{{ event.location }}</td>
  </tr>
  {% endfor %}
</table>
{% endfor %}
