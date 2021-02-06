---
title           : "07_카테고리 리스트페이지"
layout          : single
date            : 2021-02-06 + T + 14:14 + :00
categories      : "Gitblog"
tag             :
            - gitblog
            - minimal-mistakes
---
  
## 카테고리페이지
  
카테고리 페이지는 minimal-mistakes에서 잘 만들어져있다.
그렇기에 우리는 딱 3줄만 적어주면된다.
(_data/navigation.yml)

```yml
{% raw %}
main:
  - title: "Taxonomy"
    url: /categories/
{% endraw %}
```
  
이렇게만 적어주면, ```_pages/category-archive.md``` 파일과 연결되어 완성된다.
  