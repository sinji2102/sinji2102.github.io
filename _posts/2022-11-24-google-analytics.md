---
layout: post
title: "Google Analytics"
info: "유레카 프로젝트 구글 애널리틱스 관련 post"
tech: "markdown"
type: Kookmin Univ.
comment: true
---

# Googl Analytics

구글 애널리틱스(Google Analytics, GA)는 구글에서 무료로 제공하고 있는 웹분석 서비스

## 계정 생성

1.  [Google Analytics](https://analytics.google.com/analytics/web/#/)에 들어가서 계정 생성
2.  데이터 스트림 웹 항목에 본인 블로그 주소를 입력하여 스트림 추가 (측정항목은 생성 후 수정할 수 있으니 마음대로 선택)
3.  블로그에 사용할 측정 ID 확인

    - 참고로 측정 ID 형식은 다음과 같다.

      - G-XXXXXXXX 형식 ⇒ Google 애널리틱스 4 를 사용함을 뜻하고,
      - UA-XXXXXXXX-X 형식 ⇒ 유니버설 애널리틱스 를 사용함

## 블로그에 추가

나의 경우, `_config.yml`이 `google_analytics: # Tracking ID, e.g. "UA-000000-01"`이기 때문에, **유니버셜 애널리틱스**를 기준으로 진행하여야 한다.

```
# Site settings
title: github.io
# baseurl: "/ap"
url: "https://kssim.github.io"
google_analytics: G-SP2R0K5HJ4
```

---

- 스크립트는 생성한 계정 좌측 상단바 가장 하단에 위치한 `톱니바퀴모양 설정 > 속성탭 데이터 스트림 > 계정생성할때 생성했던 스크림`을 선택한다. (스트림이 없다면 우측 상단의 **스트림 추가** 버튼을 눌러 추가하자.)
- `새로운 온페이지 태그 추가` 탭의 첫번째 항목 클릭하여 소스코드를 복사한다.

```
<!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-SP2R0K5HJ4"></script>
    <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());

    gtag('config', 'G-SP2R0K5HJ4');
    </script>
```

- 블로그 폴더의 `\_includes` 로 이동하여 헤드부분을 붙이는 파일을 찾아 해당 파일에 스크립트를 삽입한다.(나의 경우 `head.html`)
- 깃허브에 수정한 소스코드를 올리고, 개발자 도구를 켜고 `gtag` 를 입력해본다.
  - 설치에 성공한 경우, `ƒ gtag(){dataLayer.push(arguments);}`이라는 메시지가 뜬다.
