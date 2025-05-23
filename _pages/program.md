---
layout: single
title: "会议日程"
permalink: /program/
header:
  overlay_image: /assets/images/banner.jpg
  overlay_filter: rgba(0, 0, 0, 0.1) # 半透明遮罩
  # caption: "Photo by [NASA](https://unsplash.com)"
---

<style>
  .abstract-container {
    display: none;
    padding: 10px;
    background-color: #f5f5f5;
    border-radius: 4px;
    margin-top: 5px;
  }
  .abstract-toggle {
    cursor: pointer;
    color: #0066cc;
  }
  .abstract-toggle:hover {
    text-decoration: underline;
  }
</style>

{% for day in site.data.schedule %}

<h2>第 {{ day.day }} 天 - {{ day.date | date: "%Y年%m月%d日" }}</h2>
<table>
  {% for event in day.events %}
  <tr>
    <td>{{ event.time }}</td>
    <td>
      <span class="abstract-toggle" onclick="toggleAbstract('abstract-{{ forloop.parentloop.index }}-{{ forloop.index }}')">
        {{ event.title }}
      </span>
      {% if event.abstract %}
        <div id="abstract-{{ forloop.parentloop.index }}-{{ forloop.index }}" class="abstract-container">
          {{ event.abstract }}
        </div>
      {% endif %}
    </td>
    <td>{{ event.speaker }}</td>
  </tr>
  {% endfor %}
</table>
{% endfor %}
