---
layout: single
title: "演讲嘉宾"
permalink: / # 页面URL
excerpt: "" # 页面摘要
header:
  overlay_image: /assets/images/banner.jpg # 页头横幅图
  overlay_filter: rgba(0, 0, 0, 0.1) # 半透明遮罩
---

## 主题报告嘉宾

<div class="speakers-grid">
  {% for speaker in site.data.speakers %}
    {% if speaker.keynote %}
      <div class="speaker-card">
        <img src="{{ speaker.avatar }}" alt="{{ speaker.name }}" class="speaker-avatar">
        <h3>{{ speaker.name }}</h3>
        <p class="speaker-affiliation">{{ speaker.affiliation }}</p>
        <div class="speaker-bio">{{ speaker.bio | markdownify }}</div>
      </div>
    {% endif %}
  {% endfor %}
</div>

## 全体演讲嘉宾

<div class="speakers-grid">
  {% for speaker in site.data.speakers %}
    <div class="speaker-card">
      <img src="{{ speaker.avatar }}" alt="{{ speaker.name }}" class="speaker-avatar">
      <h3>{{ speaker.name }}</h3>
      <p class="speaker-affiliation">{{ speaker.affiliation }}</p>
    </div>
  {% endfor %}
</div>

<style>
  /* 自定义演讲者卡片样式 */
  .speakers-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 2rem;
    margin: 2rem 0;
  }
  .speaker-card {
    border: 1px solid #eee;
    padding: 1.5rem;
    border-radius: 8px;
    text-align: center;
  }
  .speaker-avatar {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 1rem;
  }
  .speaker-affiliation {
    color: #666;
    font-style: italic;
  }
</style>
