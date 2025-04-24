---
layout: single  
title: "往年活动"
permalink: /contents/  # 页面URL
excerpt: "" 
header:
  overlay_image: /assets/images/banner.jpg  # 页头横幅图
  overlay_filter: rgba(0, 0, 0, 0.1)  # 半透明遮罩
---

{% raw %}
  {% for content in site.data.contents %}
    <h3>{{ content.year }}</h3>
    地点：<p class="speaker-affiliation">{{ content.place }}</p>
    网站：<p class="speaker-affiliation">{{ content.link }}</p>
  {% endfor %}
{% endraw %}