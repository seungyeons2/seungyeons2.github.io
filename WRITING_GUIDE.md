# 스스로를 위한 블로그 작성 가이드

## 콘텐츠 분류 (언제든 추가될 수 있음!)

### 1. **프로젝트 회고** (`_projects/` 컬렉션)

- **목적**: 포트폴리오 중심의 프로젝트 회고록
- **위치**: `_projects/` 디렉토리
- **레이아웃**: `project`
- **메뉴 접근**: "포트폴리오 (프로젝트)" → `/projects/`

### 2. **Computer Science** (`_posts/` 컬렉션)

- **목적**: 컴퓨터 과학 관련 학습 내용
- **위치**: `_posts/` 디렉토리
- **상위 카테고리**: `cs`
- **하위 카테고리**:
  - `cloud-programming`
  - `computer-architecture`
  - `nodejs`

### 3. **English Study** (`_posts/` 컬렉션)

- **목적**: 영어 학습 과정과 방법 기록
- **카테고리**: `english`
- **태그**: `vocabulary`, `grammar`, `speaking`, `writing`, `opic` 등
- **메뉴 접근**: "English Study" → `/english/`

### 4. **일상** (`_posts/` 컬렉션)

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

#### CS 관련 포스트

```yaml
---
layout: post
title: "포스트 제목"
description: >
  검색엔진용 짧은 설명~~
image:
  path: /assets/img/posts/post-slug-name/cover.jpg
categories: [cloud-programming] # 또는 [computer-architecture], [nodejs]
tags: [cs, aws, docker] # cs 태그 + 세부 기술 태그
---
```

#### 영어 공부 포스트

```yaml
---
layout: post
title: "영어 공부 제목"
description: >
  영어 학습 내용 요약
image:
  path: /assets/img/posts/post-slug-name/cover.jpg
categories: [english]
tags: [vocabulary, grammar, speaking] # 학습 영역별 태그
---
```

#### 일상 포스트

```yaml
---
layout: post
title: "일상 이야기 제목"
description: >
  일상 내용 요약
image:
  path: /assets/img/posts/post-slug-name/cover.jpg
categories: [etc]
tags: [daily, thoughts]
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

#### CS 관련

- `cs`
- `cloud-programming`: AWS, Docker, Kubernetes..
- `computer-architecture`
- `nodejs`

#### 기타

- `english`: 영어 학습
- `etc`: 일상, 개인적인 글

### 태그 (세분류)

#### CS 관련 태그

- `cs`: CS 전반
- 기술별: `aws`, `docker`, `kubernetes`, `cpu`, `memory` 등
- 학습 유형: `theory`, `practice`, `tutorial` 등

#### 영어 관련 태그

- `vocabulary`
- `grammar`
- `speaking`
- `writing`
- `reading`
- `listening`
- `opic`

#### 기타

- `daily`: 일상
- `thoughts`: 생각/감상
- `review`: 리뷰/후기

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
