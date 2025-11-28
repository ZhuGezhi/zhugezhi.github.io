---
layout: page
title: Tags
description: 内容标签导航
header-img: "img/tag-bg.jpg"
permalink: /tags/
---

<!-- 极简版标签页面，确保Jekyll构建成功 -->
<div class="simple-tags">
    <h1>所有标签</h1>
    
    <!-- 标签列表 -->
    <div class="tag-list">
        {% for tag in site.tags %}
            <div class="tag-block">
                <h2>{{ tag[0] }}</h2>
                <ul>
                    {% for post in tag[1] %}
                        <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%Y-%m-%d" }}</li>
                    {% endfor %}
                </ul>
            </div>
        {% endfor %}
    </div>
</div>

<style>
.simple-tags {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}

.tag-block {
    margin: 30px 0;
    padding: 15px;
    border: 1px solid #eee;
    border-radius: 5px;
}

.tag-block h2 {
    color: #4299e1;
    border-bottom: 1px solid #eee;
    padding-bottom: 10px;
}

.tag-block ul {
    list-style: none;
    padding: 0;
}

.tag-block li {
    padding: 8px 0;
    border-bottom: 1px dotted #eee;
}

.tag-block a {
    color: #333;
    text-decoration: none;
}

.tag-block a:hover {
    color: #4299e1;
    text-decoration: underline;
}
</style>
