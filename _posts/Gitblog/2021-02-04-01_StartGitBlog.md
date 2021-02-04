---
title           : "01_Gitblog시작하기"
layout          : single
date            : 2021-02-04 + T + 22:00 + :00
categories      : "Gitblog"
tags            :
            - gitblog
            - minimal-mistakes
---
## 깃블로그란?  
<img src="{{page.gdrive_url}}1vrQnW92cG8J2t07m7ouh2SNr8Blc_oXq"/>

**"Github"**에서 **"Github Pages"**를 통해 제공하는 기능으로, 안내설명에 따라 저장소를 구축하면 **{ https://[Repository명] }**주소를 가진 웹사이트가 생성된다.
  
해당 사이트는 "Github"의 "Repository"에 저장되어 있는 파일을 기반으로 동작하며, 페이지를 빌드하는데 다소의 시간이 소요된다.

## 템플릿  
  
보통 "Github"를 이용한 블로그 생성은 이미 만들어진 템플릿을 바탕으로 수정하여 이용하는 경우가 많으며, 아래 링크를 통해 쉽게 여러가지 템플릿을 찾을수 있다. ("minimal-mistakes" 를 선택했다.)  [Url: <a href="https://github.com/topics/jekyll-theme">https://github.com/topics/jekyll-theme</a>]
<img src="{{page.gdrive_url}}1kw37jOQZiIO0hTFxaJs7lQxI14TF30fH"/>
  
찾은 후에는 해당 템플릿 작성자의 "Repository"에 들어가 { **Fork** } 버튼을 눌러 본인의 계정에 "Repository"가 생성되고 이를 약간 수정하면 본인의 블로그가 생성된다.
<img src="{{page.gdrive_url}}16zvCM_U9kXKFrkUPBhZt3w4UxjIBDwrs"/>
  
TMI: 여기서 추천한 Jekyll-theme는 **Liquid**언어 템플릿을 사용한다.
  
## 템플릿 수정
  
Fork한 "Repsitory"에 들어간뒤  
```Settigs -> RepositoryName 을 { **[원하는 이름].github.io** }```  
로 변경하고  
<img src="{{page.gdrive_url}}1uj-w6cc8st9Gk6iAD84v5GHWgB6Enrk-"/>
  
<>Code 를 살펴보면 { **_config.yml** } 이라는 파일이 있다.
<img src="{{page.gdrive_url}}1xUHW1T9kpXxGld7B5p2ooYR0Od7HOGUE"/>

해당 파일을 클릭한 후, 연필모양의 { **Edit** }을 눌러 Github내에서 파일 수정이 가능하게 하고 **repository** 라 적힌부분에 가서 본인의 "Repository" 주소를 적어준다.  
또한, { **url** }이라 적힌 부분에는  
```"https://[본인 Repository명]/index.html"``` 를 적는다.  
이렇게 하면 "https://[본인 Repository명]" 주소로 본인의 깃블로그가 생성이 완료된다.
<img src="{{page.gdrive_url}}1VGSopGkQNIg_9PwCzMo8b-8-x6m4aDdC"/>