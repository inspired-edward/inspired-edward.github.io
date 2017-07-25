---
title: "깃허브 페이지(Github Page)와 지킬(Jekyll)로 블로그 만들기"
author_profile: true
categories:
  - howto
tags:
  - jekyll
  - github page
  - blog
---

요약
- 깃허브 테마 리스트에서 좋아하는 테마를 골라서
- 내 저장소(repository)로 fork(그대로 복사하는 거랑 비슷해요. 자세한 건 다음에)한 후
- 저장소 이름을 `USERNAME.github.io` 로 변경하면 블로그 만들기 끝.
- `/_posts/` 디렉토리 아래에 markdown형태로 블로그 글 작성

지금 쓰고 있는 이 글도 [여기](https://raw.githubusercontent.com/inspired-edward/inspired-edward.github.io/master/_posts/2017-07-24-how-to-blog.md)에 쓴 내용이 렌더링되어 나온 것입니다.

어느 정도 습관이 되고 나면 문서 스타일이나 포맷을 맞추느라 하는 산만하고 반복적인 작업을 할 필요가 없어지죠.

그럼 어떻게 설정했는지 간단하게 정리해 볼게요.

깃허브 페이지 만들기
--------------

깃허브 페이지란 자신의 깃허브의 저장소(repository)중에서 `USERNAME.github.io`라는 이름을 가지는 저장소를 말합니다.
그 이름을 가진 저장소는 웹서비스가 되도록 깃허브에서 설정해준 것이죠.(Thank you, Github!)
예를 들어 깃허브에서 `welcome-example`이란 아이디를 가지고 있다면, `welcome-example.github.io`라는 저장소를 만드는 것만으로 그 안에 있는 파일들이 `https://welcome-example.github.io`라는 주소 아래 서비스됩니다.

정해진 이름으로 저장소를 새로 생성해서 파일을 넣어도 되고, 이미 존재하는 저장소의 이름을 변경해도 상관 없습니다.
그래서 사실 지킬(Jekyll)을 이용하지 않고 깃허브 페이지만 이용해도 index.html을 비롯한 각종 파일을 업로드하면 웹서비스가 가능합니다.

하지만 여기에 Jekyll을 사용하면 markdown 문서 업로드만으로 글이 써지는 블로그가 되는 것이죠.

지킬(Jekyll)과 결합하기
------------------


