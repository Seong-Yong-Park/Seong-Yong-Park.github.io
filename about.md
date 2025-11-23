---
layout: default
title: About
---

<div class="about-container">
    <div class="about-header">
        <h1 class="about-title">About</h1>
    </div>
    
    <div class="about-content">
        <p>
            안녕하세요. 여기에 자기소개를 작성해주세요.
        </p>
        
        <h2>Contact</h2>
        <p>
            이메일: {{ site.email }}<br>
            {% if site.social.github %}
            GitHub: <a href="https://github.com/{{ site.social.github }}" target="_blank">@{{ site.social.github }}</a><br>
            {% endif %}
        </p>
    </div>
</div>

