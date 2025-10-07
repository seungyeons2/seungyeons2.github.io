---
layout: list
title: CS (Computer Science)
slug: cs
description: >
  컴퓨터 과학 관련 학습 내용을 정리합니다. 클라우드 프로그래밍, 컴퓨터 구조학, 운영체제, 알고리즘 등 전공 내용을 다룹니다.
menu: true
order: 2
---

## 🖥️ CS 학습 영역

### 클라우드 & 인프라

- **클라우드 프로그래밍**: AWS, Docker, Kubernetes..
- **DevOps**: CI/CD, 배포 자동화, 모니터링

### 시스템 & 구조

- **컴퓨터구조**:
- **운영체제**:

### 프로그래밍 & 알고리즘

- **자료구조**
- **알고리즘**

### 네트워크 & 보안

- **네트워크**
- **보안**

---

## 📚 하위 카테고리별 포스트

{% assign cs_posts = site.categories.cs %}
{% assign cloud_posts = site.categories.cloud-programming %}
{% assign architecture_posts = site.categories.computer-architecture %}
{% assign nodejs_posts = site.categories.nodejs %}

{% if cloud_posts.size > 0 %}

### 🌥️ 클라우드 프로그래밍

{% for post in cloud_posts limit:5 %}

- [{{ post.title }}]({{ post.url }}) <small>{{ post.date | date: "%Y-%m-%d" }}</small>
  {% endfor %}
  {% if cloud_posts.size > 5 %}
  [더 많은 클라우드 프로그래밍 글 보기](/cloud-programming/)
  {% endif %}
  {% endif %}

{% if architecture_posts.size > 0 %}

### 🏗️ 컴퓨터 구조

{% for post in architecture_posts limit:5 %}

- [{{ post.title }}]({{ post.url }}) <small>{{ post.date | date: "%Y-%m-%d" }}</small>
  {% endfor %}
  {% if architecture_posts.size > 5 %}
  [더 많은 컴퓨터 구조학 글 보기](/computer-architecture/)
  {% endif %}
  {% endif %}

{% if nodejs_posts.size > 0 %}

### 📗 Node.js

{% for post in nodejs_posts limit:5 %}

- [{{ post.title }}]({{ post.url }}) <small>{{ post.date | date: "%Y-%m-%d" }}</small>
  {% endfor %}
  {% if nodejs_posts.size > 5 %}
  [더 많은 Node.js 글 보기](/nodejs/)
  {% endif %}
  {% endif %}

{% if cs_posts.size > 0 %}

### 📖 기타 CS 주제

{% for post in cs_posts limit:5 %}

- [{{ post.title }}]({{ post.url }}) <small>{{ post.date | date: "%Y-%m-%d" }}</small>
  {% endfor %}
  {% endif %}
