---
title: "Jekyll theme 기반의 정적 블로그 만들기"
date: 2018-08-21
tags: [Project, Blog, Tech Blog, Jekyll, Jekyll Theme]
header:
  image: "/images/test/test.jpg"
excerpt: "YoungestSalon.github.io를 만든 방법"
mathjax: "true"
---

<br>
Jekyll theme 기반의 정적 블로그 만드는 방법을 소개합니다.<br>
본 포스팅의 내용은 [GitHub](https://github.com/YoungestSalon/TIL/blob/master/Jekyll%20theme%20%EA%B8%B0%EB%B0%98%EC%9D%98%20%EC%A0%95%EC%A0%81%20%EB%B8%94%EB%A1%9C%EA%B7%B8%20%EB%A7%8C%EB%93%A4%EA%B8%B0.md)에서도 확인하실 수 있습니다.

<br>
- **준비**
  - Git / Atom Editor 설치
  - GitHub 가입

<br>
- **GitHub에 블로그 Repository 생성**
  - Repository 이름 : 사용자 이름.github.io 형식  (*Ex. youngestsalon.github.io*)

<br>
- **Jekyll theme Repository 퍼오기**
  - Repository 주소 : https://github.com/mmistakes/minimal-mistakes
  - Git Bash에서 상기 Repository를 Clone

<br>
- **블로그 Repository에 Jekyll theme 적용**
  - Git Bash에서 블로그 Repository를 Clone
  - 전체 파일 Copy & Paste : Jekyll Repository 클론 폴더 → 블로그 Repository 클론 폴더
  - 불필요한 파일/폴더 삭제 : screenshot 파일, docs 폴더, test 폴더
  - Git Bash : git add . → git commit -m "커밋 메시지" → git push

<br>
- **블로그 환경 설정 : _config.yml 파일 수정 (@Atom Editor)**
  - Site Settings 부분 : Title, Name, Description
  - Site Author 부분 : Name, Bio, Location, GitHub, Linkedin
  - Defaults 부분(제일 하단임) : 하기 코드를 추가 후 저장

    ~~~
      # _pages
      - scope:
          path: ""
          type: pages
        values:
          layout: single
          author_profile: true
    ~~~

  - Git Bash : git add . → git commit -m "커밋 메시지" → git push

<br>
- **블로그 컨텐츠 페이지 추가**
  - 블로그 Repository 클론 폴더에 하위 폴더 3개 추가 : _posts , _pages , images
  - images 폴더에 파일 추가 : 프로필 사진, 블로그 상단 배경 사진 등
  - 이미지 jpg 파일 경로 코딩 시, 확장자 대/소문자 구분하므로 주의 필요

    ~~~
    # 컴퓨터에게 하기 두 줄의 코드는 의미가 같지 않음. (jpg와 JPG의 차이)
      image: "/images/배경화면 파일명.jpg"
      image: "/images/배경화면 파일명.JPG"  
    ~~~

  - index.html 파일 수정 (@Atom Editor) : header 부분에 하기 코드를 추가 후 저장

    ~~~
      image: "/images/배경화면 파일명.jpg"
    ~~~

  - _config.yml 파일 수정 (@Atom Editor) : author 부분의 avatar 항목 코드 변경 후 저장

    ~~~
      avatar           : "/images/프로필 사진 파일명.jpg"
    ~~~

  - about.md 파일 추가 (@Atom Editor)

    - _pages 폴더에 파일 추가 : _pages 폴더 마우스 오른쪽 버튼 클릭 → New File
    - 파일명 : about.md
    - about.md 파일 수정 (@Atom Editor) : 하기 코드를 추가 후 저장

      ~~~
      ---
      title: "About"
      permalink: /about/
      header:
        image: "/images/배경화면 파일명.jpg"
      ---

      Descriptions (자기소개 등)
      ~~~

  - machinelearning.md 파일 추가 (@Atom Editor)

    - _pages 폴더에 파일 추가 : _pages 폴더 마우스 오른쪽 버튼 클릭 → New File
    - 파일명 : machinelearning.md
    - machinelearning.md 파일 수정 (@Atom Editor) : 하기 코드를 추가 후 저장

      ~~~
      layout: archive
      permalink: /machine-learning/
      title: "Machine Learning Posts by Tags"
      author_profile: true
      header:
        image: "/images/Himalaya_backgroud.jpg"
      ~~~

  - 404.md 파일 추가 (@Atom Editor)
    - _pages 폴더에 파일 추가 : _pages 폴더 마우스 오른쪽 버튼 클릭 → New File
    - 파일명 : 404.md
    - 404.md 파일 수정 (@Atom Editor) : 하기 코드를 추가 후 저장

      ```
      ---
      title: "Page Not Found"
      layout: single
      excerpt: "Page not found. Your pixels are in anoher canvas."
      sitemap: false
      permalink: /404.html
      ---

      Sorry, but the page you were trying to view does not exist --- perhaps you can try searching for it below.

      <script type="text/javascript">
        var GOOG_FIXURL_LANG = 'en';
        var GOOG_FIXURL_SITE = '{{ site.url }}'
      </script>
      <script type="text/javascript"
        src="//linkhelp.clients.google.com/tbproxy/lh/wm/fixurl.js">
      </script>

      ```

  - _data/navigation.yml 파일 수정 (@Atom Editor) : main - title, url 부분 수정 후 저장

    ```
    main:
      - title: "About"
        url: /about/
      - title: "Machine Learning"
        url: /machine-learning/
      # - title: "About"
    ```

  - Git Bash : git add . → git commit -m "커밋 메시지" → git push

<br>
- **블로그 포스팅 추가**

  - 2018-08-20-perceptron.md 파일 추가 (@Atom Editor)
    - _posts 폴더에 파일 추가 : _posts 폴더 마우스 오른쪽 버튼 클릭 → New File
    - 파일명 : 2018-08-20-perceptron.md (즉, 날짜-주제.md 형식)
    - 2018-08-20-perceptron.md 파일 수정 (@Atom Editor) : 하기 코드를 추가 후 저장

      ```
      ---
      title: "Machine Learning Project : Perceptron"
      date: 2018-08-20
      tags: [machine learning, data science, neural network]
      header:
        image: "/images/perceptron/percept.JPG"
      excerpt: "Machine Learning, Perceptron, Data Science"
      mathjax: "true"
      ---

      # H1 Heading

      ## H2 Heading

      ### H3 Heading

      Here's some basic text.

      And here's some *italics*

      Here's some **bold** text.

      What about a [link](https://github.com/dataoptimal)?

      Here's a bulleted list:
      * First item
      + Second item
      - Third item

      Here's a numbered list:
      1. First
      2. Second
      3. Third

      Python code block:
      ​```python
          import numpy as np

          def test_function(x, y):
            z = np.sum(x,y)
            return z
      ​```

      R code block:
      ​```r
      library(tidyverse)
      df <- read_csv("some_file.csv")
      head(df)
      ​```

      Here's some inline code `x+y`.

      Here's an image:
      <img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/linsep.jpg" alt="linearly separable data">

      Here's another image using Kramdown:
      ![alt]({{ site.url }}{{ site.baseurl }}/images/perceptron/linsep.jpg)

      Here's some math:

      $$z=x+y$$

      You can also put it inline $$z=x+y$$
      ```

  - 수학 공식 서식 적용을 위한 mathjax 코드 추가

    - /_includes/scripts.html 파일 가장 아래에 하기 코드 추가 후 저장 (@Atom Editor)

      ~~~
      {% if page.mathjax %}
      <script type="text/javascript" async
        src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
      </script>
      {% endif %}
      ~~~

  - Git Bash : git add . → git commit -m "커밋 메시지" → git push

<br>
- **참조**
  - [Youtube 영상](https://www.youtube.com/watch?v=qWrcgHwSG8M)
  - [Jekyll Theme 관련 GitHub Repository](https://github.com/mmistakes/minimal-mistakes)
  - [컨텐츠 페이지 부분 코드 관련 GitHub Repository](https://github.com/dataoptimal/github-pages-tutorial)
<br>
