---
layout: default
title: Home
pagination:
  enabled: true
exclude: true
---

<h1>{{ page.title }}</h1>

<ul>
  {% for post in paginator.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}">Previous</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}">Next</a>
  {% endif %}
</div>

**Welcome to the Post-OCR Corrections Using Latin Annotations (POCULA) project.** POCULA is a text data correction project led by [Patrick J. Burns](https://isaw.nyu.edu/people/staff/patrick-burns) at NYU's [Institute for the Study of the Ancient World Library](https://isaw.nyu.edu/library). The project addresses corruption in digitized Latin texts from large repositories like Common Corpus by developing machine learning models to correct optical character recognition (OCR) errors.

POCULA aims to compile 10,000 Latin sentence pairs from Common Corpus texts, matching digitized documents to original scans where possible. The project trains interim correction models at 1,000, 2,500, and 5,000 sentence milestones. By correcting even 1% of Common Corpus's 34 billion tokens, POCULA could yield approximately 340 million tokens—among the largest available digitized Latin collections—providing a foundation for improved Latin language models.

The project uses the [LatinCy](https://huggingface.co/latincy) pretrained NLP pipelines developed by Burns to support Latin text processing.
