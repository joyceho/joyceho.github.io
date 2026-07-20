---
layout: page
permalink: /group/
title: group
description: Practical Data Mining & Exploration Lab
nav: true
nav_order: 1
---

<div class="gallery-carousel">
    <div class="gallery-track">
        {% for photo in site.data.gallery %}
        <div class="gallery-slide">
            <div class="gallery-slide-image">
                <img src="{{ photo.img | relative_url }}"
                     alt="{{ photo.caption }}"
                     loading="lazy">
            </div>
            {% if photo.caption %}
            <div class="gallery-caption">{{ photo.caption }}</div>
            {% endif %}
        </div>
        {% endfor %}
    </div>
    <button type="button" class="gallery-arrow gallery-prev" aria-label="Previous photo">&#8249;</button>
    <button type="button" class="gallery-arrow gallery-next" aria-label="Next photo">&#8250;</button>
    <div class="gallery-dots">
        {% for photo in site.data.gallery %}
        <span class="gallery-dot" aria-label="Go to photo {{ forloop.index }}"></span>
        {% endfor %}
    </div>
</div>

<script>
  (function () {
    const carousel = document.querySelector('.gallery-carousel');
    if (!carousel) return;
    const slides = carousel.querySelectorAll('.gallery-slide');
    const dots = carousel.querySelectorAll('.gallery-dot');
    let index = 0;

    function show(i) {
      index = (i + slides.length) % slides.length;
      slides.forEach((slide, n) => slide.classList.toggle('active', n === index));
      dots.forEach((dot, n) => dot.classList.toggle('active', n === index));
    }

    carousel.querySelector('.gallery-prev').addEventListener('click', () => show(index - 1));
    carousel.querySelector('.gallery-next').addEventListener('click', () => show(index + 1));
    dots.forEach((dot, n) => dot.addEventListener('click', () => show(n)));

    show(0);
  })();
</script>

We analyze and mine complex, heterogenous data to explore, characterize, and understand the underlying states / processes. Our approaches are based on statistical machine learning and data mining that work on a variety of real-life applications with a focus on healthcare applications.

We are currently a fairly large group, so we're unlikely to take on new students this year, though we wouldn't rule out an especially good fit. If you are at Emory and interested in joining our lab, send an e-mail with the subject line “More Data More Fun” and attach your CV/resume, unofficial transcript, as well as a brief description of your particular research interest to Joyce. If your email does not have the subject line, your email may not be read. We generally only consider those who have taken either Undergraduate Machine Learning (CS334) or Graduate Machine Learning (CS534). Given our current capacity, we likely won't be considering students outside Emory this year — if you are not at Emory yet, please apply to the Emory (e.g., graduate CSI program) first.


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
