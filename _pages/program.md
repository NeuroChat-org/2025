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
    display: block;
  }
  .abstract-toggle:hover {
    text-decoration: underline;
  }
  .abstract-toggle.active + .abstract-container {
    display: block; 
  }
</style>

{% for day in site.data.schedule %}

<h2>第 {{ day.day }} 天 - {{ day.date | date: "%Y年%m月%d日" }}</h2>
<table>
  {% for event in day.events %}
  <tr>
    <td>{{ event.time }}</td>
    <td>
      {% if event.speaker %}
        <div class="abstract-toggle" data-target="abstract-{{ forloop.parentloop.index }}-{{ forloop.index }}">
          {{ event.title }}
        </div>
        <div id="abstract-{{ forloop.parentloop.index }}-{{ forloop.index }}" class="abstract-container">
          {{ event.abstract }}
        </div>
      {% else %}
        {{ event.title }}
      {% endif %}
    </td>
    <td>{{ event.speaker }}</td>
  </tr>
  {% endfor %}
</table>
{% endfor %}

<script>
  // 使用事件委托提高性能
  document.addEventListener('DOMContentLoaded', function() {
    document.body.addEventListener('click', function(e) {
      const toggle = e.target.closest('.abstract-toggle');
      if (toggle) {
      
        document.querySelectorAll('.abstract-container').forEach(container => {
          if (container !== document.getElementById(toggle.getAttribute('data-target'))) {
            container.style.display = 'none';
            container.previousElementSibling.classList.remove('active');
          }
        });
      
        toggle.classList.toggle('active');
      }
    });
  });
</script>