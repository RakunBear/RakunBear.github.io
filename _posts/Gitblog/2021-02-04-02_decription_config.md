---
title           : "02_Config 설명"
layout          : single
date            : 2021-02-04 + T + 22:29 + :00
categories      : "Gitblog"
tags            :
            - gitblog
            - minimal-mistakes
---
```yml
minimal_mistakes_skin    :  스킨설정 # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
locale                   : 지역설정(정해진 단어) # "ko"
title                    : 블로그 타이틀(주소창) # "RakunBear 일지"
title_separator          : 각 타이틀이 주소창에 뜰때, 띄어스기대체 # "-"
subtitle                 : 좌상단 아래 타이틀 # "공부 저장소"
name                     : 블로그 메타 이름 # "RakunBear"
description              : 블로그 메타 설명 # "개발 & 디자인 & 기획 공부 자료를 기록합니다!"
url                      : 첫 시작 위치
baseurl                  : 기본 url값 (특별한 경우아니면 "")
repository               : Repository주소 # "https://github.com/RakunBear/RakunBear.github.io/"
teaser                   : 티저 (윗부분 이미지) <- 본 블로그에는 X
logo                     : 좌상단 로고 # "/assets/images/apple-touch-icon.png"
masthead_title           : 좌상단 위 타이틀 # "RakunBear 일지"

# Site Author
author:
  name             : "RakunBear"
  avatar           : "/assets/images/bio-photo.jpg"
  bio              : "I want to be a greate developer."
  location         : "Korea"
  links:
    # - label: "Your Website"
    #   icon: "fas fa-fw fa-link"
    #   url: "https://your-site.com"
    # - label: "Twitter"
    #   icon: "fab fa-fw fa-twitter-square"
    #   url: "https://twitter.com/"
    - label: "GitHub"                   <- 사이드 프로필 아이콘 링크
      icon: "fab fa-fw fa-github"
      url: "https://github.com/"
    # - label: "Instagram"
    #   icon: "fab fa-fw fa-instagram"
    #   url: "https://instagram.com/"

# Site Footer
footer:
  links:
    # - label: "Twitter"
    #   icon: "fab fa-fw fa-twitter-square"
    #   url: "https://twitter.com/"
    - label: "GitHub"       <- 사이트 하단 아이콘 링크
      icon: "fab fa-fw fa-github"
      url: "https://github.com/RakunBear/"
    # - label: "Instagram"
    #   icon: "fab fa-fw fa-instagram"
    #   url: "https://instagram.com/"

# Defaults      
defaults:           <- 기본 프론트 매터 변수값들
  # _posts
  - scope:
      path: "_posts"    
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: false
      share: true
      related: true
      sidebar: true
      gdrive_url: "https://drive.google.com/uc?export=view&id=" 
  # _pages
  - scope:
      path: "_pages"
      type: pages
    values:
      layout: single
      author_profile: true
      sidebar: true
  # _recipes
  - scope:
      path: "_recipes"
      type: recipes
    values:
      layout: single
      author_profile: true
      share: true
      sidebar: true
  # _pets
  - scope:
      path: "_pets"
      type: pets
    values:
      layout: single
      author_profile: true
      share: true
  # _portfolio
  - scope:
      path: "_portfolio"
      type: portfolio
    values:
      layout: single
      author_profile: false
      share: true
      sidebar: true
```