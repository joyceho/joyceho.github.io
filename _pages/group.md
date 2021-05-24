---
layout: page
permalink: /group/
title: group
description: Practical Data Mining & Exploration Lab
nav: true
---

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/group_s2021.jpg' | relative_url }}">
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/group_w2018.jpg' | relative_url }}">
    </div>
</div>
<div class="caption">
        Group photos from Spring 2021 (left) and Winter 2018 (right).
</div>

We analyze and mine complex, heterogenous data to explore, characterize, and understand the underlying states / processes. Our approaches are based on statistical machine learning and data mining that work on a variety of real-life applications with a focus on healthcare applications.

We are always looking for motivated and hard-working students (graduate and undergraduate students) to do research with us. If you are at Emory and interested in joining our lab, send an e-mail titled “More Data More Fun” with your CV, unofficial transcript, and your particular research interest to Joyce Ho. Note that we will only consider those who have taken either Undergraduate Machine Learning (CS334) or Graduate Machine Learning (CS534). If you are not at Emory yet, please apply to the CSI graduate program first.


## Members

{% assign i = 0 %}
{% for member in site.data.students %}
{% assign k = i | modulo:3 %}
{% if k == 0 %}
<div class="row">
{% endif %}    
<div class="pradax">
    <div class="thumbnail">
        {{ member.name }}
        <a href="{{ member.url }}">
        <img class="thumbnail rounded-circle" src="{{ member.img | relative_url }}"/>
        </a>
    </div>
</div>
{% assign i = i | plus:1 %}
{% assign k = i | modulo:3 %}
{% if k == 0 %}
</div>
{% endif %}    
{% endfor %}


## Alumni

<ul>
{% for member in site.data.alumni %}
    {% if member.url %}
     <li><a href="{{ member.url }}">{{ member.name }}</a>: {{ member.job }}</li>
    {% else %}
        <li>{{ member.name }}: {{ member.job }}</li>
    {% endif %}    
{% endfor %}
<ul>
