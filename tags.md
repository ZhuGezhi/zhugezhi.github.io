---
layout: page
title: Tags
description: 内容标签导航
header-img: "img/tag-bg.jpg"
permalink: /tags/
---

<!-- 简化版标签页面，兼容Jekyll 3.x -->
<div class="tags-page">
    <h1>标签索引</h1>
    
    <!-- 标签云 -->
    <div class="tag-cloud">
        {% assign tag_keys = site.tags | keys | sort %}
        {% for tag in tag_keys %}
            <a href="#tag-{{ tag | slugify }}" class="tag-item">
                {{ tag }} <span>({{ site.tags[tag].size }})</span>
            </a>
        {% endfor %}
    </div>
    
    <!-- 标签文章列表 -->
    <div class="tag-sections">
        {% for tag in tag_keys %}
            <div id="tag-{{ tag | slugify }}" class="tag-section">
                <h2>
                    <span class="tag-label">{{ tag }}</span>
                    <span class="count-badge">{{ site.tags[tag].size }} 篇文章</span>
                </h2>
                
                <ul class="post-list">
                    {% for post in site.tags[tag] %}
                        <li class="post-item">
                            <a href="{{ post.url | prepend: site.baseurl }}" class="post-link">
                                {{ post.title }}
                            </a>
                            <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
                        </li>
                    {% endfor %}
                </ul>
            </div>
        {% endfor %}
    </div>
</div>

<!-- 基础样式 -->
<style>
.tags-page {
    max-width: 900px;
    margin: 0 auto;
    padding: 20px;
    font-family: -apple-system, sans-serif;
}

.tag-cloud {
    margin: 30px 0;
    padding: 20px;
    background: #f8f9fa;
    border-radius: 8px;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

.tag-item {
    display: inline-block;
    padding: 8px 15px;
    background: white;
    border: 1px solid #e2e8f0;
    border-radius: 20px;
    text-decoration: none;
    color: #2d3748;
    font-size: 14px;
    transition: all 0.2s;
}

.tag-item:hover {
    background: #4299e1;
    color: white;
    border-color: #4299e1;
}

.tag-item span {
    color: #718096;
    margin-left: 5px;
}

.tag-item:hover span {
    color: white;
}

.tag-sections {
    margin-top: 40px;
}

.tag-section {
    margin-bottom: 40px;
    padding-bottom: 20px;
    border-bottom: 1px solid #e2e8f0;
}

.tag-section h2 {
    color: #2d3748;
    margin-bottom: 15px;
    font-size: 20px;
}

.tag-label {
    background: #4299e1;
    color: white;
    padding: 5px 12px;
    border-radius: 4px;
    margin-right: 10px;
}

.count-badge {
    font-size: 14px;
    color: #718096;
    font-weight: normal;
}

.post-list {
    list-style: none;
    padding: 0;
}

.post-item {
    padding: 10px 0;
    border-bottom: 1px solid #f0f0f0;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.post-link {
    color: #2d3748;
    text-decoration: none;
    font-size: 16px;
    transition: color 0.2s;
}

.post-link:hover {
    color: #4299e1;
}

.post-date {
    color: #718096;
    font-size: 14px;
}

/* 响应式调整 */
@media (max-width: 768px) {
    .post-item {
        flex-direction: column;
        align-items: flex-start;
        gap: 5px;
    }
}
</style>
