---
title           : "08_커스텀디자인(css적용)"
layout          : single
date            : 2021-02-06 + T + 14:22 + :00
categories      : "Gitblog"
tag             :
            - gitblog
            - minimal-mistakes
---
  
## CSS 파일 적용하는법
  
안타까울수도 있지만, minimal-mistakes테마는 ```css```파일을 사용해서 적용하지않는다.  
대신, 그것보다 좋은 ```scss(sass)```를 이용해서 디자인을 수정한다.
  
## 폰트 크기 수정
  
```FontSize``` 관해서는 assets/css/main.scss 의 파일에 

```scss
{% raw %}
---
# Only the main Sass file needs front matter (the dashes are enough)
---

@charset "utf-8";

@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin
@import "minimal-mistakes"; // main partials


// Font 변경
@import url('https://fonts.googleapis.com/css?family=Inconsolata');

html {
    font-size: 16px; // originally 16px
    @include breakpoint($medium) {
        font-size: 16px; // originally 18px
    }

    @include breakpoint($large) {
        font-size: 18px; // originally 20px
    }

    @include breakpoint($x-large) {
        font-size: 20px; // originally 22px
    }
}
{% endraw %}
```
  
형태로 적용하다록 한다.  
물론 여기에 다른 것도 덮어쓰기로 해도 되지만, 이미 나눠져 있는 파일에 작성하는걸 추천한다.  

## 다른 디자인 수정
  
```_sass``` 폴더안에 ```minimal-mistakes.scss```파일이 있을 것이다.  
여기에서 다른 ```scss``` 파일들을 import 해서 등록한다.(추가로 scss 파일을 작성하면 꼭 등록해주도록 하자. << '_'는 생략된다.)  
  
아래는 필자가 사이드카테고리에 디자인한 방법이다.
(_sass/minimal-mistakes/_sidebar.scss)
  
```scss
{% raw %}
.sidebar_taxonomy
{

  a {
    color: rgb(255, 255, 255);
    text-decoration: none;
  }

  code {
    background-color: rgb(0, 0, 0);
  }

  h2 {
    margin-top: 10%;
  }

  ul {
    margin-top: 12px;
    padding-left: 10%;
    font-size: 24px;
  }
}

{% endraw %}
```
  
`.sidebar_taxonomy` 는 클래스명이다.(`<div class="sidebar_taxonomy">`)  
아래의 나머지는 `css`와 동일하다.
