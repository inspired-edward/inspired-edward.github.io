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
깃허브 페이지와 지킬을 이용한 블로그는 처음에 설정하는 것은 어느정도 시행착오가 필요하지만 일단 설정이 끝나고 나면,
깃허브 사이트에서 작성하든, 깃허브 클라이언트 프로그램에서 작성을 하든 일단 markdown형태로 글을 작성한 후
`USERNAME.github.io/_posts/` 디렉토리 안에 넣어주면 새 글이 생성됩니다.

지금 쓰고 있는 이 글도 [여기](https://raw.githubusercontent.com/inspired-edward/inspired-edward.github.io/master/_posts/2017-07-24-how-to-blog.md)에 쓴 내용이 렌더링되어 나온 것입니다.

어느 정도 습관이 되고 나면 문서 스타일이나 포맷을 맞추느라 하는 산만하고 반복적인 작업을 할 필요가 없어지죠.

그럼 어떻게 설정했는지 간단하게 정리해 볼게요.

깃허브 페이지 만들기
--------------

요약
- 깃허브에 USERNAME.github.io 라는 저장소(repository)를 만든다
- 끝.

깃허브 페이지란 자신의 깃허브의 저장소(repository)중에서 `USERNAME.github.io`라는 이름을 가지는 저장소를 말합니다.
그 이름을 가진 저장소는 웹서비스가 되도록 깃허브에서 설정해준 것이죠.
예를 들어 깃허브에서 `welcome-example`이란 아이디를 가지고 있다면, `welcome-example.github.io`라는 저장소를 만드는 것만으로 그 안에 있는 파일들이 `https://welcome-example.github.io`라는 주소 아래 서비스됩니다.

그래서 사실 지킬(Jekyll)을 이용하지 않고 깃허브 페이지만 이용해도 index.html을 비롯한 각종 파일을 업로드하면 웹서비스가 가능합니다.

하지만 여기에 Jekyll을 사용하면 markdown 문서 업로드만으로 글이 써지는 블로그가 되는 것이죠.

지킬(Jekyll)과 결합하기
------------------

요약
- 잘 만들어진 지킬(Jekyll) 테마를 찾아 그 테마 소스를 fork(그대로 받아옴)한다
- 받아온 저장소(repository) 이름을 `USERNAME.github.io`으로 바꾼다
- 끝.
- `USERNAME.github.io/_posts/`디렉토리 아래에 markdown형태로 글을 쓴다

