---
layout: single
# title: "Welcome!"
permalink: /
header:
  overlay_image: /assets/images/banner.jpg
  overlay_filter: rgba(0, 0, 0, 0.1)  # 半透明遮罩
  # caption: "Photo by [NASA](https://unsplash.com)"
---
<div class="full">
## 会议简介
{{ site.description }}

### 重要日期
- **会议日期**：{{ site.conference.date }}

### 会议地点
**{{ site.conference.venue.name }}**  
地址：{{ site.conference.venue.address }}  
[查看地图]({{ site.conference.venue.map_link }}){: .btn .btn--info}
{% if site.conference.venue.photo %}
![会场照片]({{ site.conference.venue.photo }}){: .align-right width="40%"}
{% endif %}

[查看日程](/program/){: .btn .btn--info}
</div>