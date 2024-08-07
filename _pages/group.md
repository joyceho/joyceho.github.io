---
layout: page
permalink: /group/
title: group
description: Practical Data Mining & Exploration Lab
nav: true
nav_order: 1
---

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/group_s2023.png' | relative_url }}">
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/group_s2022.jpg' | relative_url }}">
    </div>
</div>
<div class="caption">
        Group photos from Spring 2023 (left) and Spring 2022 (right).
</div>

We analyze and mine complex, heterogenous data to explore, characterize, and understand the underlying states / processes. Our approaches are based on statistical machine learning and data mining that work on a variety of real-life applications with a focus on healthcare applications.

We are always looking for motivated and hard-working students (graduate and undergraduate students) to do research with us. If you are at Emory and interested in joining our lab, send an e-mail with the subject line “More Data More Fun” and attach your CV/resume, unofficial transcript, as well as a brief description of your particular research interest to Joyce. If your email does not have the subject line, your email may not be read. We generally only consider those who have taken either Undergraduate Machine Learning (CS334) or Graduate Machine Learning (CS534). If you are not at Emory yet, please apply to the Emory (e.g., graduate CSI program) first.


## Members

{% assign sorted_students = site.data.students| sort: "name" %}
<div class="row row-cols-1 row-cols-md-4">
    {% for member in site.data.students %}
        <div class="col">
            <div class="card-body text-center">
                <h6 class="card-title">{{ member.name }}</h6>
            </div>
            <a href="{{ member.url }}">
            <div class="card h-50 hoverable">
            {% if member.img  %}
                {%
                include figure.liquid
                loading="eager"
                path=member.img
                sizes = "100px"
                alt="student thumbnail"
                class="card-img-bottom"
                %}
            {% endif %}
            </div>
            </a>
        </div>
        {% endfor %}
</div>

## Alumni

Graduated members of the group and their first stop post-graduation.

<ul>
{% for member in site.data.alumni %}
    {% if member.url %}
     <li><a href="{{ member.url }}">{{ member.name }} ({{ member.year }})</a>: {{ member.job }}</li>
    {% else %}
        <li>{{ member.name }} ({{ member.year }}): {{ member.job }}</li>
    {% endif %}    
{% endfor %}
<ul>
