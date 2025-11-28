---
layout: page
title: Tags
header-img: "img/tag-bg.jpg"
permalink: /tags/
---

<div class="tags-page">
    <h1>标签索引</h1>
    
    <div class="tag-cloud">
        {% for tag in site.tags %}
            <a href="#tag-{{ tag[0] }}" class="tag-item">
                {{ tag[0] }} <span>({{ tag[1].size }})</span>
            </a>
        {% endfor %}
    </div>
    
    <div class="tag-sections">
        {% for tag in site.tags %}
            <div id="tag-{{ tag[0] }}" class="tag-section">
                <h2>
                    <span class="tag-label">{{ tag[0] }}</span>
                    <span class="count-badge">{{ tag[1].size }} 篇文章</span>
                </h2>
                
                <ul class="post-list">
                    {% for post in tag[1] %}
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
        
        {% if site.tags.size == 0 %}
        <div class="no-tags-message">
            <i class="fa fa-folder-open-o"></i>
            <h3>暂无标签</h3>
            <p>发布文章并添加标签后，这里会显示标签列表</p>
        </div>
        {% endif %}
    </div>
</div>

<style>
.tags-page {
    max-width: 900px;
}

.tag-cloud {
    margin: 30px 0;
    padding: 20px;
    background: white;
    border-radius: 8px;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    box-shadow: var(--shadow);
}

.tag-item {
    display: inline-block;
    padding: 8px 15px;
    background: var(--light-gray);
    border-radius: 20px;
    text-decoration: none;
    color: var(--primary-color);
    font-size: 14px;
    transition: var(--transition);
}

.tag-item:hover {
    background: var(--accent-color);
    color: white;
    transform: translateY(-3px);
    box-shadow: 0 4px 12px rgba(66, 153, 225, 0.3);
}

.tag-item span {
    color: var(--secondary-color);
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
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: var(--shadow);
}

.tag-section h2 {
    color: var(--primary-color);
    margin-bottom: 15px;
    font-size: 20px;
}

.tag-label {
    background: var(--accent-color);
    color: white;
    padding: 5px 12px;
    border-radius: 4px;
    margin-right: 10px;
}

.count-badge {
    font-size: 14px;
    color: var(--secondary-color);
    font-weight: normal;
}

.post-list {
    list-style: none;
    padding: 0;
}

.post-item {
    padding: 10px 0;
    border-bottom: 1px solid var(--border-color);
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.post-item:last-child {
    border-bottom: none;
}

.post-link {
    color: var(--primary-color);
    text-decoration: none;
    font-size: 16px;
    transition: color 0.2s;
}

.post-link:hover {
    color: var(--accent-color);
}

.post-date {
    color: var(--secondary-color);
    font-size: 14px;
}

.no-tags-message {
    text-align: center;
    padding: 60px 20px;
    color: var(--secondary-color);
}

.no-tags-message i {
    font-size: 60px;
    margin-bottom: 20px;
    color: var(--border-color);
}

@media (max-width: 768px) {
    .post-item {
        flex-direction: column;
        align-items: flex-start;
        gap: 5px;
    }
}
</style>
