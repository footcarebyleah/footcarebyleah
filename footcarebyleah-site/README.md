# 리아풋케어 Hugo 사이트

Jekyll에서 Hugo로 변환된 리아풋케어 블로그입니다.

## 설치 방법

1. Hugo 설치 (https://gohugo.io/installation/)
2. 이 디렉토리로 이동
3. 개발 서버 실행:
   ```bash
   hugo server -D
   ```

## 사이트 구조

```
footcarebyleah-hugo/
├── hugo.toml              # 사이트 설정
├── content/
│   └── blog/              # 블로그 포스트
├── static/
│   └── images/            # 이미지 파일
└── themes/
    └── footcare-theme/    # 커스텀 테마
        ├── layouts/
        │   ├── _default/
        │   │   ├── baseof.html    # 기본 레이아웃
        │   │   ├── list.html      # 목록 페이지
        │   │   └── single.html    # 개별 포스트
        │   ├── partials/
        │   │   ├── header.html    # 헤더
        │   │   └── footer.html    # 푸터
        │   └── index.html         # 홈페이지
        └── theme.toml
```

## 블로그 포스트 작성

새 포스트는 `content/blog/` 디렉토리에 마크다운 파일로 작성합니다.

Front matter 예시:
```yaml
---
title: "포스트 제목"
description: "포스트 설명"
date: 2025-01-29
categories: ["발톱케어", "발톱무좀"]
tags: ["발톱무좀", "무좀약"]
image: "/images/post-image.jpg"
author: "리아풋케어"
draft: false
---
```

## 배포

GitHub Pages에 배포하려면:

1. 사이트 빌드:
   ```bash
   hugo
   ```

2. `public/` 디렉토리의 내용을 GitHub Pages 저장소에 푸시

## 주요 변경사항

Jekyll에서 Hugo로 변환하면서 변경된 사항:

- `_config.yml` → `hugo.toml`
- `_posts/` → `content/blog/`
- `_layouts/` → `themes/footcare-theme/layouts/`
- Jekyll의 Liquid 템플릿 → Hugo의 Go 템플릿
- Front matter 날짜 형식 변경
- 이미지 경로: `static/images/` → `assets/images/` (Hugo 이미지 처리 사용)
  - 자동 리사이징 및 WebP 변환
  - 최적화된 이미지 로딩

## 이미지 사용 방법

이미지는 `assets/images/` 폴더에 넣으면 Hugo가 자동으로 최적화합니다:

- 히어로 이미지: 1920px 너비로 리사이징
- 프로필 이미지: 800px 너비로 리사이징  
- 블로그 썸네일: 600x400px로 리사이징
- 블로그 본문 이미지: 1200px 너비로 리사이징
- 모두 WebP 포맷으로 자동 변환 (용량 절감)

포스트에서 이미지 사용:
```yaml
image: "images/your-photo.jpg"  # /를 빼고 작성
```

## 디자인 색상

- 메인 컬러: #87A96B (연한 초록)
- 호버 컬러: #6d8a55 (진한 초록)
