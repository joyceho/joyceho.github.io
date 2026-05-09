---
layout: page
permalink: /group/
title: group
description: Practical Data Mining & Exploration Lab
nav: true
nav_order: 1
---

<div class="grid">
    {% for photo in site.data.gallery %}
    <div class="grid-item" style="width: calc(50% - 5px);">
        <div class="card hoverable mb-2">
            <img src="{{ photo.img | relative_url }}"
                 class="card-img-top img-fluid"
                 data-zoomable
                 alt="{{ photo.caption }}"
                 loading="lazy">
            {% if photo.caption %}
            <div class="card-footer text-center p-1">
                <small class="text-muted">{{ photo.caption }}</small>
            </div>
            {% endif %}
        </div>
    </div>
    {% endfor %}
</div>

We analyze and mine complex, heterogenous data to explore, characterize, and understand the underlying states / processes. Our approaches are based on statistical machine learning and data mining that work on a variety of real-life applications with a focus on healthcare applications.

We are always looking for motivated and hard-working students (graduate and undergraduate students) to do research with us. If you are at Emory and interested in joining our lab, send an e-mail with the subject line “More Data More Fun” and attach your CV/resume, unofficial transcript, as well as a brief description of your particular research interest to Joyce. If your email does not have the subject line, your email may not be read. We generally only consider those who have taken either Undergraduate Machine Learning (CS334) or Graduate Machine Learning (CS534). If you are not at Emory yet, please apply to the Emory (e.g., graduate CSI program) first.


## Members

{% assign sorted_students = site.data.students| sort: "name" %}
<div class="row row-cols-1 row-cols-md-4 student-card-wrapper">
    {% for member in site.data.students %}
        <div class="col mb-4">
            <a href="{{ member.url }}">
                <div class="card hoverable">
                    {% if member.img %}
                        <img src="{{ member.img | relative_url }}" 
                             alt="{{ member.name }}" 
                             loading="eager"
                             class="card-img-top">
                    {% endif %}
                    <div class="card-body text-center">
                        <h6 class="card-title mb-0">{{ member.name }}</h6>
                        {% if member.co_advised_with %}
                            <small class="text-muted">co-advised with {{ member.co_advised_with }}</small>
                        {% endif %}
                    </div>
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
