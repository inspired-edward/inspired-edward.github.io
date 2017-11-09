---
title: "깃허브 페이지(GitHub Page)와 지킬(Jekyll)로 블로그 만들기"
excerpt: "한 번 따라가 봅시다."
toc: true
toc_label: "이 페이지에는"
toc_icon: "gear"
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
- 저장소 이름을 `USERNAME.github.io` 로 변경하면 블로그 만들기 끝
- `/_posts/` 디렉토리 아래에 markdown형태로 블로그 글 작성

지금 쓰고 있는 이 글도 [여기](https://raw.githubusercontent.com/inspired-edward/inspired-edward.github.io/master/_posts/2017-07-24-how-to-blog.md)에 쓴 내용이 렌더링되어 나온 것입니다.

어느 정도 습관이 되고 나면 문서 스타일이나 포맷을 맞추느라 하는 산만하고 반복적인 작업을 할 필요가 없어지죠.

그럼 깃허브 페이지(GitHub Page)와 지킬에 대해서 간략하게만 알아보고 실제로 어떻게 설정하는지 훑어보겠습니다. 방법만 따로 보고 싶으시면 맨 아래쪽 요약 페이지로 가셔도 됩니다.

깃허브 페이지(GitHub Page) 만들기
----------------------------

깃허브 페이지(GitHub Page)란 자신의 깃허브(GitHub)의 저장소(repository) 중에서 `USERNAME.github.io`라는 이름을 가지는 저장소를 말합니다.
그 이름을 가진 저장소는 웹서비스가 되도록 깃허브(GitHub)에서 설정해준 것이죠. (Thank you, GitHub!)
예를 들어 깃허브(GitHub)에서 `welcome-example`이란 아이디를 가지고 있다면, `welcome-example.github.io`라는 저장소를 만드는 것만으로 그 안에 있는 파일들이 `https://welcome-example.github.io`라는 주소 아래 서비스됩니다.

정해진 이름으로 저장소를 새로 생성해서 파일을 넣어도 되고, 이미 존재하는 저장소의 이름을 변경해도 상관없습니다.
그래서 사실 지킬(Jekyll)을 이용하지 않고 깃허브 페이지(GitHub Page)만 이용해도 index.html을 비롯한 각종 파일을 올리면 웹서비스가 가능합니다.
하지만 이렇게만 하면 웹페이지를 로컬에서 미리 다 만들어 놓은 다음 FTP나 SFTP로 올리던 시절이랑 별 차이가 없겠죠. 자주 업데이트되지 않는 사이트라면 이것만으로도 충분합니다.

하지만 여기에 지킬(Jekyll)을 사용하면 markdown 문서 업로드만으로 쉽게 글을 쓸 수 있는 블로그가 되는 것이죠.

지킬(Jekyll)과 결합하기
-------------------

지킬(Jekyll)은 루비(Ruby)기반으로 만들어진 웹사이트 생성기입니다. 정해진 템플릿으로 글을 작성한 후에 지킬(Jekyll) 명령을 수행하면 모두 렌더링해서 웹페이지를 만들어줍니다.

좋은 소식은 깃허브 페이지(GitHub Page)에서 지킬(Jekyll)을 지원하기 때문에 정해진 경로에(보통 `/_posts/`) markdown 형식으로 글을 작성하면 따로 지킬(Jekyll) 명령을 내리지 않아도 깃허브(GitHub)에서 알아서 렌더링 된 웹페이지를 보여준다는 것이죠. (Thank you again, GitHub!)

두 가지 방식으로 지킬(Jekyll) 웹사이트를 만들 수 있습니다.
### 직접 컴퓨터에서 웹사이트를 빌드한 다음 깃허브(GitHub) 저장소에 올리는 방법
가장 많이 하는 방법이지만 생각보다 시간이 오래 걸립니다. *로컬 컴퓨터에 루비 등의 언어 및 패키지를 설치하는 작업* 이 시행착오가 많은 작업이고, 깃허브(GitHub)에서 지원하는 루비 및 패키지 버전과 로컬 컴퓨터의 *버전이 다를 수 있기* 때문이죠.

(그래도 웹사이트를 처음부터 빌드하면 자신에게 맞게 고칠 여지가 많죠. 궁금하신 부분은 [지킬(Jekyll) 한글 설명 페이지](http://jekyllrb-ko.github.io/)에서 답을 찾을 수 있을 겁니다.)

### 테마 찾아서 Fork 하는 방법
이미 블로그를 다 빌드한 다음 공개해 놓은 곳이 많습니다. [jekyllthemes.org](http://jekyllthemes.org/)도 그중 하나입니다.
![Jekyll Themes](https://lh3.googleusercontent.com/8ox-i8KzoYo3i1KZFS5bvBi9eZeasGP6zP6ns6nlM4b1UL5QQYjzu3vS0CdvWABMBKDmScQfqbwI3ZRansQthAB_JZgGllDOgtntXDnf5u-C8TA8wRM7WTXxpnSXFEwCMPMEBHaeIDTt0HdxZxNv5_b7c7eVRCfCREVZm37Eu4p7rXS0pDICXszTmTBOCsS3afWtF4TNcMfHEXFUjl3S4AylqSQsqv76vQe0mB9J4K1VwYtGiBfFFuJQvKkaiQLIBsSzIsKXL4SmyFhgTEnNWcRG-O4kYWvFKzOmJBPPPX_LqpD5J7vFRwtu0SD0OTMberw2jOreDmCz_L5PlWcl-RFfW8K3FgHCbe8qqeTuwNKhiql1-QIkqMdhrwERfCJOHaca701lyLl_dH1oRohj1GbJ93-N9iVtERQzaukgAbrUMck9IS1TrB3E0zmMCbJhHItOX-I3RVGHsR3WUeghmNicCPRgFD8O9g0HlaA_DFkjnftllJddylGbZvVuWHacQPQw6ERrF7f2JJt-Tef_un2TGrNRJS_MHqQzdoAnU2MgQRGMebmPQm358iDXSoD9_J3vbNXN_oZI5vJWIjxcK8dZzt6cF2lHYB8hLi4wiyASpXn7Qk6kZqx2IXJeuim_D8i3wdyvzRg6R5GR3L9PaGRMRZqTR-tteDT4breA_7xG=w879-h514-no)
원하는 테마 하나를 찾아서 fork(복사와 비슷한 개념) 한 다음,
![Fork](https://lh3.googleusercontent.com/-hatD5rxwWGNnw0To73KlfEuRhdIDtebto1QFcjmuriL6sxkwlF19VPdT6J7PTN122bgyMqK-fHYLW0KbxfeoH4QPe3XZP4Ol1Z6UNjN5-kj94fU7OqBEWyVCwrGRWtHWUyByZU8D9ogaeoYgZtmCR0oxSB-VFN7jmNujESVd__Vx-1PKUv1NRU17awP_OdSsKYqT9BOJdn2EqtILZcjoV-VoG9cLBiXhmhdiglLy3hxdf-KecSq71f1-XT7BFJthjfDl52rmJHL-uAR-ZVpDgJ9naofAfNbWY55RBSgLdqWH1TI0HB9euO3Wk2Lkou2HlXSnGjuQqzTzx7fNMehsLCXaXQ13PhjGnhER3d4R8nOloVAnTzZGgmopF9GY5vFG1tn0e3rVnbCYjGHsQK9glwyM7QNvXhyh5dyHsM9TR8DZ7I2fnji28JqNkVTncTLUmjw3BA40DaLneptnuKKeNiDcKB0eA6lbBrNRY3xYQz3EfYUDlSbqU9257-5gfiJ2vi7Dh3uI3jUYsy7X0D82QOEe7Xec3Qvju1BHNoExU_BJfHKzP91vNduFWH7_B8IgD9ndefedIvKeCCMxW1WyMuOo2NxxX9FXzDAt7EFmQ-BGxd3yy8JLj-RM794L92SRJKPUgYyWqMer2Cp5L6nMuUVaV4YrIxdh2gyRIUS04Oy=w784-h146-no)

Fork 된 저장소의 설정(Settings) 탭으로 가서 이름만 `USERNAME.github.io` 형태로 변경하면 된답니다.

![저장소 이름 변경](https://lh3.googleusercontent.com/UYWM4RBmcI2_8lPpcZat75wDXqpwC9bBdZjEzX7BI1jANj3lyquABD1b9bXsv6XlkZ9H85Jzs_j5_h9Wfd5ay9DGoNoxx221MSTXMq6SjOmFA-VN51Q_fANsNA6Ee7xPwxO_VwkR1X2PSXoY6bytsnV_nPSZNQxrvAUfeD-WXzO3wjEFZ3xWiOUoPGK9QPkbEcfq-GgaubsOzN1V9rur9Ij9E0XQXFbTqVkt07tuHlVeCEQ79UnojM0p0EDXJPZJ-xmOvsnGC_G3THlI2eeDqjxEw2a0dzppxHyKXkfZFMgkCAb9g-aVe6qEiVXDDxeD0L5ECr-Kx8W_s4d5wJp4ULlgkLj9UK0_IrTXUSCWWOK6rMKLLTiXhMMp-w6COihKrUozm1mQqFECrDAPpsFkT24vWkTs_LJxgx4Elg20bPZDR0wRwGlxkuJH_A17egDG_mJOXPAEizVGBGCrJq4xFhp974jYHTgiyvIlRL1re4bg0EOBRyybTPfW-LB6s5uGTf9_NNR3NRd3zmG_Mdk6Rgbr0rsMwY2KB6GjprYve8MFAvMp-uQmS2KoUvAYFlMw2670az2zb72_4AoPwMV_n455BUcTaBeVovbkhohJ2Gk2oZdOnWQCLaCI6barza4WHFRF6c8of6mCoYvLTRAkIHOkxoiNPd-jIn2bmwGQ_suA=w738-h288-no)

따로 지킬(Jekyll) 빌드를 할 필요도 없고, 이것만으로 `https:/USERNAME.github.io`에 블로그가 서비스되기 시작합니다.

글쓰기
----

### 글을 저장하는 위치

지킬(Jekyll)에서는 `/_posts/` 디렉토리 아래에 markdown 형태로 글을 쓰면 된다고 했습니다.

### 파일 확장자
다만 파일 이름은 특정 형식을 지켜서 만들어줘야 합니다.

`YYYY-MM-DD-글제목.확장자`

이 글의 파일 이름은 `2017-07-24-how-to-blog.md` 입니다. 다시 말해서, 글을 쓴 날짜가 글을 발행하거나 완성한 날짜로 자동설정되는 것이 아니라, 파일 이름에 따로 씁니다. 이 부분은 사람에 따라 불편할 수도 있겠네요.

### 머리말
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
Front Matter에서 지원하는 필드는 지킬(Jekyll) 테마마다 다릅니다. *title* 과 *layout* 은 보통 공통으로 지원하는데요. 제 경우에는 layout을 이미 테마 기본 설정에서 정해버렸기 때문에 나머지를 설정합니다.

지킬 한글 페이지의 [머리말](http://jekyllrb-ko.github.io/docs/frontmatter/)에서 더 자세한 설명을 볼 수 있습니다.

### 내용 작성
Front Matter 아래에 본인이 원하는 글 내용을 markdown으로 작성합니다.
markdown 형식을 다 배운 다음에 글 쓰겠다고 마음먹지 마세요. 일단 글을 쓰신 후에, 제목 형식은 어떻게 설정하는지, 링크는 어떻게 거는지 등등을 검색으로 알아보시기 바랍니다. markdown 문법은 아주 단순해서 쓰면서 자연스레 익혀집니다.

그래도 혹시 모르니 [마크다운 사용법](https://gist.github.com/ihoneymon/652be052a0727ad59601) 하나 링크합니다.


요약
---

1. 아직 안 되어 있다면 [github.com](github.com) 가입
 - 처음 가입하면 기본적인 깃허브(Github) 사용법을 Step-by-Step으로 알려줍니다.
2. 구글 검색을 하거나, 지킬 테마 사이트 [jekyllthemes.org](jekyllthemes.org) 에서 원하는 테마를 Fork
3. Fork된 저장소(repository)이름을 `USERNAME.github.io` 형태로 변경
 - 변경한 즉시 `https://USERNAME.github.io`에 블로그가 서비스 되기 시작합니다.
4. `/_posts/` 디렉토리 아래에 글 작성
 - 파일 이름 형식은 `YYYY-MM-DD-글제목.확장자`
 - Front Matter로 글의 제목, 레이아웃, 및 그 외 테마에서 지원하는 변수 설정
 - Markdown 형태로 글쓰기

남은 일
-----

블로그 제목도 정해야 할 것 같고, 구글에 검색도 되어야 할 것 같고... 블로그를 다 만들고 나면 빈 구멍들이 여기저기 보일 겁니다. 기존에 사용하던 블로그 전용 사이트들이 기본 기능을 얼마나 잘 구현해 놓았는지 새삼 느끼게 되죠.

하지만, 이 블로그는 **무료** 이고, **자유도** 가 높고, 테마 설정을 포함한 블로그 설정은 초기에만 할 거니까, 약간의 불편함을 참고 구글 검색을 합니다.

### 블로그 초기 설정

저장소(repository)에 보면, `_config.yml` 이란 파일이 떡 하니 자리 잡고 있을 겁니다. 여기에서 블로그에서 지원하는 거의 모든 기능을 설정할 수 있습니다. 파일 안에 코멘트로 설명이 잘 되어 있습니다. 원하는 기능만 켜고 나머지는 그대로 두면 됩니다.

기본적으로
- 블로그 제목
- 블로그 주소
  - `USERNAME.github.io` 랑 같게 설정해 둡니다
- 블로그의 키워드

등을 설정합니다. 블로그 테마에 따라서 댓글 기능이나, SNS 공유 기능도 켜거나 끌 수 있습니다.

### 댓글(comments) 기능

깃허브 페이지(Github Page)는 정적 사이트이기 때문에, 댓글 기능을 사용하려면 외부서비스를 끌어다와야 합니다. 가장 유명한 것은 [DISQUS](https://disqus.com/)을 사용하는 겁니다. 이 블로그도 DISQUS를 사용하고 있습니다.

[DISQUS](https://disqus.com/)에 가입하신 다음, Step-by-Step 가이드에 나오는 script를 블로그 layout을 형성하는 html 파일을 찾아서 삽입해 주시면 됩니다. 제가 지금 사용하는 테마는 DISQUS를 자체 지원하고 있어서, DISQUS가입 이후에 `_config.yml` 에서 DISQUS항목을 활성화하는 것만으로 댓글 기능을 추가할 수 있었습니다.

후기
---

이 정도만 해도 블로그에 글 쓰는 데에는 충분한 환경이 마련됩니다. 글을 좀 더 쓰다 보면, 블로그 내에서 검색하고 싶기도 할 테고, 태그만 따로 정리된 페이지를 만든다던가, 카테고리별로 페이지를 따로 만든다든가 하는 작업을 할 필요성을 느끼게 되겠지요. (인간의 욕심은 끝이 없고...) 직접 만들어도 될 테고, 아마도 지킬 테마의 어딘가에 비활성화되어서 숨어 있을 테니 필요할 때마다 찾아서 켜면 될 것으로 기대합니다.
