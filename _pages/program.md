---
layout: single  # 使用单栏布局
title: "会议日程"
permalink: /program/
---

{% raw %}
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
{% endraw %}
