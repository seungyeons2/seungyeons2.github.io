---
layout: default
title: Portfolio Projects
description: >
  진행했던 주요 프로젝트들의 기술적 도전과 학습 내용을 정리했습니다.
---

# 🚀 프로젝트 포트폴리오

이곳에는 제가 진행한 다양한 프로젝트들이 모여 있습니다. 각 프로젝트에서 마주했던 기술적 도전, 해결 과정, 그리고 배운 점들을 상세히 기록했습니다.

---

{% for project in site.projects %}
## [{{ project.title }}]({{ project.url }})

{{ project.description }}

{% if project.links %}
**관련 링크:**
{% for link in project.links %}
- [{{ link.title }}]({{ link.url }})
{% endfor %}
{% endif %}

---
{% endfor %}

{% if site.projects.size == 0 %}
## 준비 중입니다... 🚧

곧 멋진 프로젝트들을 업로드할 예정입니다!

프로젝트를 추가하려면:
```bash
bundle exec jekyll compose project "프로젝트 제목"
```
{% endif %}
