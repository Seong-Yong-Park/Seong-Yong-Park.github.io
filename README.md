# Seong-Yong Park's Portfolio & Blog

Jekyll과 GitHub Pages를 사용한 개인 포트폴리오 및 블로그 사이트입니다.

## 사이트 구조

- **Landing Page** (`index.html`): Resume 섹션과 최근 블로그 포스트 미리보기
- **Blog** (`blog.html`): 카테고리별 블로그 포스트 목록
- **About** (`about.md`): 소개 페이지

## 블로그 포스트 작성 방법

1. `_posts/` 폴더에 새로운 마크다운 파일을 생성합니다.
2. 파일명 형식: `YYYY-MM-DD-title.md` (예: `2024-01-15-my-post.md`)
3. 파일 상단에 Front matter를 추가합니다:

```yaml
---
layout: post
title: "포스트 제목"
date: 2024-01-15
categories: [카테고리명]
description: "포스트 설명"
---
```

4. 카테고리는 배열로 여러 개 지정할 수 있습니다: `categories: [Development, Frontend]`

## 커스터마이징

### 사이트 정보 수정
`_config.yml` 파일에서 사이트 제목, 설명, 이메일 등을 수정할 수 있습니다.

### Resume 내용 수정
`_layouts/home.html` 파일의 Resume 섹션을 수정하세요.

### 스타일 수정
`assets/css/main.css` 파일에서 색상, 폰트, 레이아웃 등을 커스터마이징할 수 있습니다.

## 로컬에서 테스트하기

Jekyll을 로컬에서 실행하려면:

```bash
# Jekyll 설치 (Ruby 필요)
gem install bundler jekyll

# 의존성 설치
bundle install

# 로컬 서버 실행
bundle exec jekyll serve
```

브라우저에서 `http://localhost:4000`으로 접속하여 확인할 수 있습니다.

## GitHub Pages 배포

이 레포지토리는 GitHub Pages로 자동 배포됩니다. `main` 브랜치에 푸시하면 자동으로 사이트가 업데이트됩니다.

