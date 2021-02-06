---
title           : "06_사이드카테고리"
layout          : single
date            : 2021-02-06 + T + 13:46 + :00
categories      : "Gitblog"
tag             :
            - gitblog
            - minimal-mistakes
---
  
## Side Category List
  
[05_카테고리]({% post_url /Gitblog/2021-02-06-05_Category %})에서 작성한 카테고리 페이지들로 들어갈 수 있는 사이드 리스트를 만들어 볼 것이다.

## _includes/taxonomy/taxonomy-list.html 작성
  
minimal-mistakes에 이미 ```_includes/category-list.html```이 있지만, 원하는 기능하고는 다르므로 구분될 수 있는 이름인 ```_includes/taxnomy/taxonomy-list.html```파일을 만들어 준다.  
  
``` html
{% raw %}
{% assign sorted_categories = site.categories | sort %}
<ul>
    {% for category in sorted_categories %}
        {% assign c_name = category[0] %}
        {% assign c_size = category[1].size %}
        {% if c_name != null %}
            {% include taxonomy/taxonomy-item.html category_name = c_name category_size = c_size%}
        {% endif %}
    {% endfor %}
</ul>
{% endraw %}
```
  
```assign```은 변수를 만드는 것이고, ```site.categories```는 사이트내에서 categories변수의 값의 집합을 불러온다. (집합이므로 중복된 값이 존재할 수 없다.) ```| sort```부분은 이를 아스키코드 순으로 정렬해준다.
  
여기서 ```category```의 0번 요소는 이름, 1번 요소는 해당 categories를 가지는 페이지 전체 리스트를 가진다.  
이때, ```c_name, c_size```로 변수에 다시 할당한 이유는 include의 알규먼트로 보내기 위해서이다.(그냥 넣으면 되지않는다.)
  
## _include/taxonomy/taxonomy-item.html 작성
  
``` html
{% raw %}
<div id={{include.category_name}}>
    <li>
        <code>
            <a href = "/{{include.category_name}}">
                {{include.category_name}} ({{include.category_size | minus: 1}})
            </a>
        </code>
    </li>
</div> 
{% endraw %}
```
  
받는 파라미터는 ```include.파라미터명```으로 받을 수 있다.({% raw %}{{변수}}{% endraw %})를 쓰면 해당 값을 출력한다.  
여기서 ```| minus: 1```이 있는 이유는 필자는 모든 카테고리의 포스터에 1개의 더미파일을 넣어서 0개의 포스터 개수를 표시해 주고 싶었기 때문이다.

## _includes/sidebar.html 수정
  
위에서 완성한 카테고리 항목 리스트를 이제 사이드바에 넣어줄 것이다. (_includes/sidebar.html)
  
``` html
{% raw %}
{% if page.author_profile or layout.author_profile or page.sidebar %}
  <div class="sidebar sticky">
  {% if page.author_profile or layout.author_profile %}{% include author-profile.html %}{% endif %}
  {% if page.sidebar %}
    {% for s in page.sidebar %}
      {% if s.image %}
        <img src="{{ s.image | relative_url }}"
             alt="{% if s.image_alt %}{{ s.image_alt }}{% endif %}">
      {% endif %}
      {% if s.title %}<h3>{{ s.title }}</h3>{% endif %}
      {% if s.text %}{{ s.text | markdownify }}{% endif %}
      {% if s.nav %}{% include nav_list nav=s.nav %}{% endif %}
    {% endfor %}
    {% if page.sidebar.nav %}
      {% include nav_list nav=page.sidebar.nav %}
    {% endif %}

    <div class="sidebar_taxonomy">
      <h2>Taxonomy</h2>
      {% include taxonomy/taxonomy-list.html %}
    </div>

  {% endif %}
  </div>
{% endif %}
{% endraw %}
```
  
아래 부분만 신경써주면 된다.
  
```html
{% raw %}
<div class="sidebar_taxonomy">
    <h2>Taxonomy</h2>
    {% include taxonomy/taxonomy-list.html %}
</div>
{% endraw %}
```
  