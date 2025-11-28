---
layout: page
title: "About"
description: "Hey, this is L's Thought Hub."
header-img: "img/post-bg-rwd.jpg"
permalink: /about/
---

<!-- About Page Content -->
<div class="about-container">
    <!-- Language Selector -->
    <div class="language-selector">
        <button id="btn-zh" class="lang-btn active">中文</button>
        <button id="btn-en" class="lang-btn">English</button>
    </div>

    <!-- Chinese Version -->
    <div id="content-zh" class="content-section">
        <blockquote>
            <p>心外无物 心外无理<br>
            知是行之始 行是知之成</p>
        </blockquote>

        <p>Hey，我是<strong>卤汁(Lorne)</strong>，INFJ-T,统计学在读本科生。</p>

        <p>爱好：胡思乱想、摄影、羽毛球。</p>

        <p>突然想搭建一个属于自己的博客，所以借助GitHub上@qiubaiying的快速教程，成功搭建了L's Thought Hub。原创博主的GitHub主页是<a href="https://github.com/qiubaiying" target="_blank" rel="noopener noreferrer">👉GitHub·BY</a> 与 简书主页<a href="http://www.jianshu.com/u/e71990ada2fd" target="_blank" rel="noopener noreferrer">👉BY</a>。</p>
        
        <h5>Talks</h5>

        <ul>
            <li><a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a></li>
            <li><a href="http://jekyll.com.cn/" target="_blank" rel="noopener noreferrer">jekyll</a></li>
            <li><a href="http://huangxuan.me/" target="_blank" rel="noopener noreferrer">Hux</a></li> 
            <li><a href="https://analytics.google.com/analytics" target="_blank" rel="noopener noreferrer">Google Analytics</a></li>
        </ul>
    </div>

    <!-- English Version -->
    <div id="content-en" class="content-section">
        <blockquote>
            <p>Nothing exists outside the mind; no truth exists outside the mind.<br>
            Knowledge is the beginning of action; action is the completion of knowledge.</p>
        </blockquote>

        <p>Hi, I am <strong>Lorne</strong>, an INFJ-T undergraduate student majoring in Statistics.</p>

        <p>This is my personal blog, built with GitHub Pages and Jekyll using the quick tutorial by @qiubaiying on GitHub. 👉 <a href="https://github.com/qiubaiying" target="_blank" rel="noopener noreferrer">Github·BY</a>.</p>
        
        <p>I am an enthusiast of mind-wandering, photography, and badminton.</p>

        <h5>Talks</h5>

        <ul>
            <li><a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a></li>
            <li><a href="http://jekyll.com.cn/" target="_blank" rel="noopener noreferrer">Jekyll</a></li>
            <li><a href="https://pages.github.com/" target="_blank" rel="noopener noreferrer">GitHub Pages</a></li>
            <li><a href="https://zhugezhi.icu/" target="_blank" rel="noopener noreferrer">My Blog</a></li>
        </ul>
    </div>
</div>

<!-- JavaScript -->
<script>
// 确保DOM加载完成后执行
document.addEventListener('DOMContentLoaded', function() {
    // 获取DOM元素
    const btnZh = document.getElementById('btn-zh');
    const btnEn = document.getElementById('btn-en');
    const contentZh = document.getElementById('content-zh');
    const contentEn = document.getElementById('content-en');
    
    // 默认显示中文，隐藏英文
    contentZh.style.display = 'block';
    contentEn.style.display = 'none';
    
    // 中文按钮点击事件
    btnZh.addEventListener('click', function() {
        contentZh.style.display = 'block';
        contentEn.style.display = 'none';
        btnZh.classList.add('active');
        btnEn.classList.remove('active');
    });
    
    // 英文按钮点击事件
    btnEn.addEventListener('click', function() {
        contentZh.style.display = 'none';
        contentEn.style.display = 'block';
        btnZh.classList.remove('active');
        btnEn.classList.add('active');
    });
});
</script>

<!-- CSS Styles -->
<style>
/* 基础容器样式 */
.about-container {
    max-width: 900px;
    margin: 20px auto;
    padding: 0 20px;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    line-height: 1.8;
    color: #333;
}

/* 语言选择器 */
.language-selector {
    margin-bottom: 30px;
    display: flex;
    gap: 12px;
}

.lang-btn {
    padding: 10px 24px;
    border: 1px solid #ddd;
    border-radius: 25px;
    background: #fff;
    color: #333;
    cursor: pointer;
    font-size: 16px;
    transition: all 0.3s ease;
}

.lang-btn.active {
    background: #4299e1;
    color: #fff;
    border-color: #4299e1;
}

.lang-btn:hover:not(.active) {
    border-color: #4299e1;
    color: #4299e1;
}

/* 内容区块 */
.content-section {
    padding: 25px;
    background: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
}

/* 引用样式 */
blockquote {
    border-left: 4px solid #4299e1;
    padding: 15px 20px;
    margin: 20px 0;
    background: #f8f9fa;
    border-radius: 4px;
    font-style: italic;
}

/* 标题样式 */
h5 {
    color: #4299e1;
    margin-top: 30px;
    margin-bottom: 15px;
    font-size: 1.3em;
}

/* 列表样式 */
ul {
    padding-left: 25px;
}

li {
    margin-bottom: 10px;
}

/* 链接样式 */
a {
    color: #4299e1;
    text-decoration: none;
    border-bottom: 1px solid transparent;
    transition: border-color 0.3s;
}

a:hover {
    border-bottom: 1px solid #4299e1;
}

/* 强调文本 */
strong {
    color: #2d3748;
}

/* 响应式设计 */
@media (max-width: 768px) {
    .about-container {
        padding: 0 15px;
    }
    
    .content-section {
        padding: 15px;
    }
    
    .lang-btn {
        padding: 8px 18px;
        font-size: 14px;
    }
}
</style>

<!-- Gitalk Comment System -->
{% if site.gitalk.enable == true %}
<link rel="stylesheet" href="https://unpkg.com/gitalk/dist/gitalk.css">
<script src="https://unpkg.com/gitalk/dist/gitalk.min.js"></script>
<div id="gitalk-container" style="margin-top: 40px;"></div>
<script>
const gitalk = new Gitalk({
    clientID: '{{ site.gitalk.clientID }}',
    clientSecret: '{{ site.gitalk.clientSecret }}',
    repo: '{{ site.gitalk.repo }}',
    owner: '{{ site.gitalk.owner }}',
    admin: ['{{ site.gitalk.admin }}'],
    id: 'about-page',
    distractionFreeMode: false
});
gitalk.render('gitalk-container');
</script>
{% endif %}
