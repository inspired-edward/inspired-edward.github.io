---
title: "깃허브 페이지(GitHub Page)와 지킬(Jekyll)로 블로그 만들기"
comments: true
author_profile: true
categories:
  - howto
tags:
  - jekyll
  - github page
  - blog
---

결론적으로
- 깃허브(GitHub) 테마 리스트에서 좋아하는 테마를 골라서
- 내 저장소(repository)로 fork(그대로 복사하는 거랑 비슷해요. 자세한 건 다음에)한 후
- 저장소 이름을 `USERNAME.github.io` 로 변경하면 블로그 만들기 끝.
- `/_posts/` 디렉토리 아래에 markdown형태로 블로그 글 작성

지금 쓰고 있는 이 글도 [여기](https://raw.githubusercontent.com/inspired-edward/inspired-edward.github.io/master/_posts/2017-07-24-how-to-blog.md)에 쓴 내용이 렌더링되어 나온 것입니다.

어느 정도 습관이 되고 나면 문서 스타일이나 포맷을 맞추느라 하는 산만하고 반복적인 작업을 할 필요가 없어지죠.

그럼 깃허브 페이지(GitHub Page)와 지킬에 대해서 간략하게만 알아보고 실제로 어떻게 설정하는지 훑어보겠습니다. 방법만 따로 보고 싶으시면 맨 아래쪽 요약 페이지로 스크롤 내리셔도 됩니다.

{% include toc %}

깃허브 페이지(GitHub Page) 만들기
----------------------------

깃허브 페이지(GitHub Page)란 자신의 깃허브(GitHub)의 저장소(repository)중에서 `USERNAME.github.io`라는 이름을 가지는 저장소를 말합니다.
그 이름을 가진 저장소는 웹서비스가 되도록 깃허브(GitHub)에서 설정해준 것이죠.(Thank you, GitHub!)
예를 들어 깃허브(GitHub)에서 `welcome-example`이란 아이디를 가지고 있다면, `welcome-example.github.io`라는 저장소를 만드는 것만으로 그 안에 있는 파일들이 `https://welcome-example.github.io`라는 주소 아래 서비스됩니다.

정해진 이름으로 저장소를 새로 생성해서 파일을 넣어도 되고, 이미 존재하는 저장소의 이름을 변경해도 상관 없습니다.
그래서 사실 지킬(Jekyll)을 이용하지 않고 깃허브 페이지(GitHub Page)만 이용해도 index.html을 비롯한 각종 파일을 업로드하면 웹서비스가 가능합니다.
하지만 이렇게만 하면 웹페이지를 로컬에서 미리 다 만들어 놓은 다음 FTP나 SFTP로 업로드 하던 시절이랑 별 차이가 없겠죠. 자주 업데이트 되지 않는 사이트라면 이것만으로도 충분합니다.

하지만 여기에 지킬(Jekyll)을 사용하면 markdown 문서 업로드만으로 쉽게 글을 쓸 수 있는 블로그가 되는 것이죠.

지킬(Jekyll)과 결합하기
-------------------

지킬(Jekyll)은 루비(Ruby)기반으로 만들어진 웹사이트 생성기입니다. 정해진 템플릿으로 글을 작성한 후에 지킬(Jekyll) 명령을 수행하면 모두 렌더링해서 웹페이지를 만들어줍니다.

좋은 소식은 깃허브 페이지(GitHub Page)에서 지킬(Jekyll)을 지원하기 때문에 정해진 경로에(보통 `/_posts/`) markdown 형식으로 글을 작성하면 따로 지킬(Jekyll) 명령을 내리지 않아도 깃허브(GitHub)에서 알아서 렌더링된 웹페이지를 보여준다는 것이죠. (Thank you again, GitHub!)

두 가지 방식으로 지킬(Jekyll) 웹사이트를 만들 수 있습니다.
### 직접 컴퓨터에서 웹사이트를 빌드한 다음 깃허브(GitHub) 저장소에 올리는 방법
가장 많이 하는 방법이지만 생각보다 시간이 오래 걸립니다. *로컬 컴퓨터에 루비 등의 언어 및 패키지를 설치하는 작업* 이 시행착오가 많은 작업이고, 깃허브(GitHub)에서 지원하는 루비 및 패키지 버전과 로컬 컴퓨터의 *버전이 다를 수 있기* 때문이죠.

(그래도 웹사이트를 처음부터 빌드하면 자신에게 맞게 고칠 여지가 많죠. 궁금하신 부분은 [지킬(Jekyll) 한글 설명 페이지](http://jekyllrb-ko.github.io/)에서 답을 찾을 수 있을 겁니다.)

### 테마 찾아서 Fork하는 방법
이미 블로그를 다 빌드한 다음 공개해 놓은 곳이 많습니다. [jekyllthemes.org](http://jekyllthemes.org/)도 그 중 하나입니다.
![Jekyll Themes](https://lh3.googleusercontent.com/REu1IAdWIylsAIO-6nZmzMOodXhj7xwqlSr23O6Kj6e6Gr3qHNoBnZUevh4E-BEICByNKDfxT_OVLLB-lbVq3Rageeep9ReSrWfxOGcdA4eytIFvNlWCqIxzd6atwFrjkcyZTV7GbrYmWbZY_eGgBtJG7c0uzvUagRHynmM_FOnYeRqLCV9jXZPtDB1c7kJhUUyYCfz2zgd5bW5FKE23N9CikqRHUlKiYmetBsIe6Cw9mEOCxtT2sZscsV0kgPLR24U5eF5GYUQKagtaG9WMMvb6LokaBs1Pt6EzpJmckmbMuKO3kFzNRDpqvrJrBkoxi1S-sdouVaTfj_qyypQl8NKF9Q1Li6mzWLGjiAIIt483odKZWh4pBvmQLgT5a2GLAINAb6zL9oL6rXYMQYYsdzNMdwr7RUpOYbK_7wwiZfJ9GIzgTpBa2s1J6erEKa12ie-EK600ZP9lB6LwmWs5Bhb25ePnnoAZkD5ACHhLMyP6K9mu5Wd3xogIedYA-PNJ9HXmKhKZ3nSqior6H3m_TOUmKn2viF5fPUn-BZzfU-bzlfHJj4Uwc5_U4B0b87R1gbwGbcc4LwVdJJsDesTNvEJ0PioNlB65q5--Fourp3q0z46FCwA=w2188-h1280-no)
원하는 테마 하나를 찾아서 fork(복사와 비슷한 개념)한 다음,
![Fork](https://lh3.googleusercontent.com/iARzs-8pq1z5T6keNyOgWx2YuY25aaERNTROJr9EfsDbgHYdX-fG0c6-v79vsaQfWBTp1u5zUgxlLT3gq3QGHTp774AWFft83Ibn1lg1Nsbp-ojI7vQu1jN2-U9sg_KxSmSe5pwV905vHfdDZZFs_uK4BFkj3CBwTtQWldQ3WuXmbOe7s0z7AECLN4QONsjSTbfybGXG3x0TLwgbnvlxFStLhUO7q-G5FFO7vwOZjl3RPOFaYGXzePgQn4lWcfS00Lx2GW0H-qbUi03v3gq47z_YtpjjmORKbNY6_2tkSrybwRj6amcCxJpAp_3eON_MOJzoRCERTLRHtiha2Qq2vpCzStAQ2F1-QJLCK1iqukhUdw9Lq5BsW2Rhd9ndKYOTnRvXqKcHKGTsNzISrPt6RfHZLWSbxXTE4i90b-Z1_CJH--sasYwJyN4ZFQ6rzTKsmEHra6adjzAYQ8JJvj2GpcFuWlYaeSn1HybXwuo-hVigHkaqwbbebyOe949jdPN5LW1v0a-EjBN_n00WqcioYzikPPts4QWp3UV0hynknoKIbHT1oqRCBC02X_f64Qj8_wur3tHi4_RHTDcnycxYjfvHp-Qa7FI3GOe1m5OsemAnB4uesIE=w784-h146-no)

Fork된 저장소의 설정(Settings) 탭으로 가서 이름만 USERNAME.github.io 형태로 변경하면 된답니다.

![저장소 이름 변경](https://lh3.googleusercontent.com/tBMfZWo1a_mSJTLc2ZeCXboosq1n-Ru9-SrCD-8ZMvyjx6w64FB95J45kv27SZDi_M6zXcNnt4MuLdmHPQAefArf6qcU5r-sVdFVN7UwxQl1LldO1AXhozmZ5KFtvOkP_HN2_4SkVPM3hyB-6QjOHtO-RZjdg3zAnXOhqPtN55kfjH1WDauJegjLmXiTYSBJM7yJhlyED6HKQFgmZ7HeqsFJ9hbxy4hxpGVAK4XdhMR7LAQZWXBc2xqkLJjGV2UsNIJPpOGuNoIIzoyPMDQAa_g5cWuJts56Eb2_hM8Nc5WJcsH6wdGdcZ1-ruviEfSTKGk9MQ8aXwp-616jYoXLXyyL82Ks0_AcK2TdQ6mLXRU6OQWT-UNH3Wmu9uSa3hdOTHoligFQBlItlipYw-8ZedoKyl_r3u9qONntGHwBMFde9VqsGIrPyt33UW0b9Al50cxUHqTXdFTX99fPvZZ3Wi5GArqi7TFZnll9MPjgfeBXwtJ9cImDAddJwnVPCyALfyonJ941AmwyAFGdEIga1WFL98PZHOWJ6rzLEJGc1QAq56lnZWeDlaQWaWVTFLd9nUOotAwRvY-RKiUdrJ8GmkJl8wrcmyc5Y353CxkS6RtCugdot90=w738-h288-no)

따로 지킬(Jekyll) 빌드를 할 필요도 없고, 그것만으로 끝이죠. 가장 간단하게 Jekyll + GitHub 블로그를 시작하는 방법입니다.

글쓰기
----

### 글을 저장하는 위치

지킬(Jekyll)에서는 `/_posts/` 디렉토리 아래에 markdown형태로 글을 쓰면 된다고 했습니다.

### 파일 확장자
다만 파일 이름은 특정 형식을 지켜서 만들어줘야 합니다.

`YYYY-MM-DD-글제목.확장자`

이 글의 파일 이름은 `2017-07-24-how-to-blog.md` 입니다. 다시 말해서, 글을 쓴 날짜가 글을 발행하거나 완성한 날짜로 자동설정되는 것이 아니라, 파일 이름에 따로 씁니다. 이 부분은 사람에 따라 불편할 수도 있겠네요.

### 머릿말
본격적으로 글을 쓰기 전에 글이 들어가는 페이지의 기본사항을 적어주게 됩니다. **Front Matter** 라고 부릅니다. 이 글의 Front Matter는 아래와 같이 되어 있습니다.
```
---
title: "깃허브 페이지(GitHub Page)와 지킬(Jekyll)로 블로그 만들기"
comments: true
author_profile: true
categories:
  - howto
tags:
  - jekyll
  - github page
  - blog
---
```
Front Matter에서 지원하는 필드는 지킬(Jekyll) 테마마다 다릅니다. *title* 과 *layout* 은 보통 공통적으로 지원하는데요. 제 경우에는 layout을 이미 테마 기본 설정에서 정해버렸기 때문에 나머지를 설정합니다.

지킬 한글 페이지의 [머릿말](http://jekyllrb-ko.github.io/docs/frontmatter/)에서 더 자세한 설명을 볼 수 있습니다.

### 내용 작성
Front Matter 아래에 본인이 원하는 글 내용을 markdown으로 작성합니다.
markdown 형식을 다 배운 다음에 글 쓰겠다고 마음먹지 마세요. 일단 글을 쓰신 후에, 제목 형식은 어떻게 설정하는지, 링크는 어떻게 거는 지 등등을 검색으로 알아보시기 바랍니다. markdown문법은 아주 단순해서 쓰면서 자연스레 익혀집니다.

그래도 혹시 모르니 [마크다운 사용법](https://gist.github.com/ihoneymon/652be052a0727ad59601) 하나 링크합니다.


요약
---

1. 아직 안 되어 있다면 [github.com](github.com) 가입
 - 처음 가입하면 기본적인 깃허브(Github)사용법을 Step-by-Step으로 알려줍니다.
2. 구글 검색을 하거나, 지킬 테마 사이트 [jekyllthemes.org](jekyllthemes.org) 에서 원하는 테마를 Fork
3. Fort된 저장소(repository)이름을 `USERNAME.github.io` 형태로 변경
 - 변경한 즉시 `https://USERNAME.github.io`에 블로그가 서비스 되기 시작합니다.
4. `/_posts/` 디렉토리 아래에 글 작성
 - 파일 이름 형식은 `YYYY-MM-DD-글제목.확장자`
 - Front Matter로 글의 제목, 레이아웃, 및 그 외 테마에서 지원하는 변수 설정
 - Markdown 형태로 글 쓰기

남은 일 들
--------

블로그 제목도 정해야 할 것 같고, 구글에 검색도 되어야 할 것 같고... 블로그를 다 만들고 나면 빈 구멍들이 여기저기 보일 겁니다. 기존에 사용하던 블로그 전용 사이트들이 기본 기능을 얼마나 잘 구현해 놓았는지 새삼 느끼게 되죠.

하지만, 이 블로그는 **무료** 이고, **자유도** 가 높고, 테마 설정을 포함한 블로그 설정은 초기에만 할 거니까, 약간의 불편함을 참고 구글 검색을 합니다.

### 블로그 초기 설정

저장소(repository)에 보면, `_config.yml` 이란 파일이 떡 하니 자리잡고 있을 겁니다. 여기에서 블로그에서 지원하는 거의 모든 기능을 설정할 수 있습니다. 파일 안에 코멘트로 설명이 잘 되어 있습니다. 원하는 기능만 켜고 나머지는 그대로 두면 됩니다.

기본적으로
- 블로그 제목
- 블로그 주소
 - `USERNAME.github.io` 랑 같게 설정해 둡니다
- 블로그의 키워드

등을 설정합니다. 블로그 테마에 따라서 댓글 기능이나, SNS공유 기능도 켜거나 끌 수 있습니다.

### 댓글(comments) 기능

깃허브 페이지(Github Page)는 정적 사이트이기 때문에, 댓글 기능을 사용하려면 외부서비스를 끌어다와야 합니다. 가장 유명한 것은 [DISQUS](https://disqus.com/)을 사용하는 겁니다. 이 블로그도 DISQUS를 사용하고 있습니다.

[DISQUS](https://disqus.com/)에 가입하신 다음, Step-by-Step 가이드에 나오는 script를 블로그 layout을 형성하는 html파일을 찾아서 삽입해 주시면 됩니다. 제가 지금 사용하는 테마는 DISQUS를 자체 지원하고 있어서, DISQUS가입 이후에 `_config.yml` 에서 DISQUS항목을 활성화하는 것만으로 댓글 기능을 추가할 수 있었습니다.

후기
---

이 정도만 해도 블로그에 글쓰는데에는 충분한 환경이 마련됩니다. 글을 좀 더 쓰다 보면, 블로그 내에서 검색을 하고 싶기도 할 테고, 태그만 따로 정리된 페이지를 만든다던가, 카테고리별로 페이지를 따로 만든다던가 하는 작업을 할 필요성을 느끼게 되겠지요. 직접 만들어도 될테고, 아마도 지킬 테마의 어딘가에 비활성화되어서 숨어 있을 테니 필요할 때마다 찾아서 켜면 될 것으로 기대합니다.
