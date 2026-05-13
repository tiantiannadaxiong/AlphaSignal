---
layout: default
title: AlphaSignal
---

<div class="hero">
  <h1>AlphaSignal</h1>
  <div class="tagline">全球金融市场日报速读</div>
  <div class="author-line">
    <svg viewBox="0 0 512 512" width="14" height="14"><path d="M488.6 104.1c16.7 18.1 24.4 39.5 23.3 65.5v202.4c-.4 26.4-9.2 48.1-26.5 65.1-17.2 17-39.1 25.9-65.5 26.7H92.02c-26.45-.8-48.21-9.8-65.28-27.2C9.682 419.4.767 397.5.968 371.7V169.2c-2.009-25.2 7.445-47.4 28.362-66.4l31.17-27.1 61.6-53.7c10.2-8.8 22.5-13.2 36.9-13.2 14.4 0 26.7 4.4 36.9 13.2l20.6 17.9h104l20.6-17.9c10.2-8.8 22.5-13.2 36.9-13.2 14.4 0 26.7 4.4 36.9 13.2l61.6 53.7 31.2 27.1zM390.3 159.1H121.7c-11.3 0-20.5 9.2-20.5 20.5v192.8c0 11.3 9.2 20.5 20.5 20.5h268.6c11.3 0 20.5-9.2 20.5-20.5V179.6c0-11.3-9.2-20.5-20.5-20.5zM221.3 313.6c-11.3 0-20.5-9.2-20.5-20.5v-48.2c0-11.3 9.2-20.5 20.5-20.5 11.3 0 20.5 9.2 20.5 20.5v48.2c0 11.3-9.2 20.5-20.5 20.5zm69.4 0c-11.3 0-20.5-9.2-20.5-20.5v-48.2c0-11.3 9.2-20.5 20.5-20.5 11.3 0 20.5 9.2 20.5 20.5v48.2c0 11.3-9.2 20.5-20.5 20.5z"/></svg>
    <a href="https://space.bilibili.com/3461580037556673?spm_id_from=333.788.0.0" target="_blank" rel="noopener">天天拿大熊 @ B站</a>
  </div>
</div>

<div id="reports" class="section">
  <div class="section-title">最新日报</div>
  <div class="report-list">
  {% assign reports = site.posts | sort: "git_added" | reverse %}
  {% for report in reports limit: 9 %}
    <article class="report-item">
      {% if report.venue %}
      <div class="cat">{{ report.venue }}</div>
      {% endif %}
      <h3><a href="{{ report.url | relative_url }}">{{ report.title }}</a></h3>
      <div class="meta">
        <time datetime="{{ report.date | date_to_xmlschema }}">{{ report.date | date: "%Y-%m-%d" }}</time>
        <span class="meta-sep">·</span>
        <span class="git-time">提交 {{ report.git_added | date: "%m-%d %H:%M" }}</span>
      </div>
      {% if report.description %}
      <div class="excerpt">{{ report.description }}</div>
      {% endif %}
    </article>
  {% endfor %}
  </div>
</div>

<div class="section">
  <div class="section-title">关于 AlphaSignal</div>
  <div class="intro-text">
    <strong>AlphaSignal</strong> 是一份每日金融市场速读，覆盖全球宏观、股票、固定收益、外汇与大宗商品等核心资产类别。我们提炼当日最重要的市场事件与机构观点，让你在五分钟内把握市场脉络。<br><br>
    在这里，我们不追求信息量，而追求<strong>信号质量</strong>。每一篇日报都是一次对市场噪音的过滤。<br><br>
    本站由 <span style="color: var(--ft-pink); font-weight: 500;">天天拿大熊@B站</span> 策划与维护，内容同步更新于 Bilibili 与 GitHub。
  </div>
</div>
