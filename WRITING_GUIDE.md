# 스스로를 위한 블로그 작성 가이드

## 콘텐츠 분류 (언제든 추가될 수 있음!)

### 1. **프로젝트 회고** (`_projects/` 컬렉션)

- **목적**: 포트폴리오 중심의 프로젝트 회고록
- **위치**: `_projects/` 디렉토리
- **레이아웃**: `project`
- **메뉴 접근**: "포트폴리오 (프로젝트)" → `/projects/`

### 2. **기술 문서/CS 공부** (`_posts/` 컬렉션)

- **목적**: CS 지식, 기술 학습 내용
- **위치**: `_posts/` 디렉토리
- **카테고리**: `cloud-programming`, `nodejs` 등
- **태그**: `study`, 기술별 태그
- **메뉴 접근**: "기술 문서 (CS Study)" → `/cloud-programming/`

### 3. **일상 잡담** (`_posts/` 컬렉션)

- **목적**: 개인적인 생각, 일상 기록
- **카테고리**: `etc`
- **메뉴 접근**: "일상 잡담 (ETC)" → `/etc/`

## 글쓰기 워크플로우

### Jekyll Compose

#### 새 포스트 작성

```bash
bundle exec jekyll compose post "새로운 포스트 제목"
```

#### 새 프로젝트 회고 작성

```bash
bundle exec jekyll compose project "프로젝트 회고 제목"
```

### 프론트 매터 예시

#### 포스트 (기술 문서/일상)

```yaml
---
layout: post
title: "포스트 제목"
description: >
  검색엔진용 짧은 설명~~
image:
  path: /assets/img/posts/post-slug-name/cover.jpg
categories: [cloud-programming] # 또는 [etc]
tags: [study, aws, docker]
---
```

#### 프로젝트 회고

```yaml
---
layout: project
title: "프로젝트 이름"
description: >
  프로젝트에 대한 짧은 설명
image:
  path: /assets/img/projects/project-slug-name/cover.jpg
links:
  - title: GitHub Repository
    url: https://github.com/username/project
  - title: Live Demo
    url: https://project-demo.com
featured: true # 메인 페이지 노출 여부
---
```

## 이미지 첨부 워크플로우

### 저장 경로 규칙

- **포스트 이미지**: `/assets/img/posts/<post-slug-name>/`
- **프로젝트 이미지**: `/assets/img/projects/<project-slug-name>/`

### 디렉토리 생성 예시

```bash
mkdir -p assets/img/posts/my-postpostttt

mkdir -p assets/img/projects/my-projectprojecttt
```

### 이미지 삽입

#### 기본

```markdown
![이미지 설명](/assets/img/posts/my-post-slug/image.jpg)
```

#### 성능 최적화된 이미지

```markdown
![이미지 설명](/assets/img/posts/my-post-slug/image.jpg){:width="1200" height="800" loading="lazy"}
```

#### 커버

```yaml
image:
  path: /assets/img/posts/my-post-slug/cover.jpg
  srcset:
    1x: /assets/img/posts/my-post-slug/cover.jpg
    2x: /assets/img/posts/my-post-slug/cover@2x.jpg
```

## 태그 및 카테고리

### 카테고리 (대분류)

- `cloud-programming`: AWS, Docker, Kubernetes 등 클라우드/인프라
- `nodejs`: Node.js, JavaScript 관련
- `etc`: 일상, 개인적인 글

### 태그 (세분류)

- `study`: 학습 내용
- 기술별: `aws`, `docker`, `react`, `typescript` 등
- 프로젝트별: `portfolio`, `web-development` 등

## 이미지 권장사항

### 이미지 크기

- **커버**: 1200x630px
- **본문**: 최대 1200px
- **썸네일**: 400x300px

### 파일 형식

- **사진**: JPEG
- **그래픽/스크린샷**: PNG
- **아이콘**: SVG (웬만하면 지켜봅시다!!)

## 배포 전 체크리스트

1. **이미지 최적화**: 파일 크기 확인 (각 이미지 < 500KB 권장)
2. **메타데이터**: description, image 경로 확인
3. **태그/카테고리**: 일관성 있게
4. **링크 확인**: 모든 내부/외부 링크 동작 확인
5. **미리보기**: `bundle exec jekyll serve`
