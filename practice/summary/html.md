# HTML
- 웹사이트는 텍스트로 이루어진 파일이다.
- 우리가 작성한 코드를 브라우저가 읽고 화면에 그려준다.
- 웹사이트는 HTML, CSS, JS로 구성되며 HTML로 구조를 표시하고, CSS로 디자인, JS로 여러가지 기능을 추가할 수 있다.
- 웹사이트는 HTML만으로도 구성이 가능하지만, 모든 디자인은 CSS에서 만들어 진다.
  그렇기에 HTML, CSS는 한세트로 움직이며, CSS만으로 웹사이트를 구현하는 것은 불가능하다.

## HTML(Hypertext Markup Language)

- 링크로 연결된 텍스트를 의미하는 Hypertext와 태그 등의 기호를 이용해 문서작성을 도와주는 Markup Language를 합하여 만들어졌다. 확장자는 `.html`

- HTML은 브라우저에서 오류를 보여주지 않는다. 잘못된 문법으로 작성해도 브라우저에 content를 그대로 보여준다.

- HTML은 Markup Language로 보는게 합당하다. 태그 자체가 어떤 기능을 가진다기 보단 포스트잇 처럼 구분하는것에 가깝고, 그를 통해 CSS JS가 각 요소에 속성을 부여하기 쉽게 만든다.

## HTML 문서 구조

HTML 문서는 `<head>`와 `<body>`로 구성된다.

`<head>`: 문서의 메타데이터를 담는 부분. \
브라우저가 어떻게 문서를 렌더링할 것인가, 문서의 제목은 무엇인가, 외부 파일을 어떻게 연결할 것인가에 대한 정보를 담고있다. \
`<html>`태그의 바로아래 `<body>`태그의 전에 위치 해야한다.

`<body>`: 웹 페이지의 실제 내용을 담는 부분. \
텍스트, 이미지, 링크, 표, 목록 등 다양한 웹 요소들이 위치하며, `<body>` 태그 내부의 내용을 실제로 브라우저에 렌더링되어 보여지는 곳이다. `<body>` 태그는 웹 페이지의 본문을 정의하기 때문에 여러 HTML 요소를 포함할 수 있다.

## Elements (요소)

- HTML을 구성하는 구성하는 문자열. 다음과 같은 구조로 작성된다.

  ```html
  <tag attribute="attribute-value">content</tag>
  ```

  - `tag`: 태그. `content`를 둘러싸고 있다. 위와 같은 구조에선 `tag`요소라고 부르기도 한다.
  - `attribute`: 속성. `tag`에 부여되는 정보들을 의미한다.
  - `content`: 내용. 브라우저에서 보여지는 부분. `tag`와 `attribute`에 적힌 속성 값에 영향을 받는다.


## Tag (태그)
- 브라우저에서 보여지는 부분인 `content`를 둘러싸고 있는 문자열.

### 대표적인 Tag
    
- 텍스트: 제목(`<h1>`, `<h2>`, `<h3>` ...), 단락(`<p>`), 강조(`<strong>`, `<em>`), 등
- 미디어: 이미지(`<img>`), 비디오(`<video>`), 오디오(`<audio>`), 등
- **하이퍼링크**: `<a>`
- 리스트: 순서 없는 리스트(`<ul>`), 순서 있는 리스트(`<ol>`), 등
- 표: `<table>`, `<theadd>`, `<tbody>`, `<th>`, `<tr>`, `<td>`, 등
- 폼: `<form>`, `<input>`, `<button>` `<textarea>`, 등
- 의미없는 태그: `<div>`, `<span>`

### Tag 상속 구조
- `tag`는 `tag`안에 존재할 수 있으며 이를 가족관계도에 빗대어 표현하기도 한다

  - 조상 : 대상 태그에 직접 연관되며 상위에 존재하는 모든 태그.
  - 부모 : 대상 태그에 바로 위에 존재하는 태그.
  - 형제 : 대상 태그와 같은 부모 태그를 보유한 모든 태그.
  - 자식 : 대상 태그의 바로 밑에 존재하는 모든 태그.
  - 자손 : 대상 태그의 직접 연관되며 하위에 존재하는 모든 태그.

  ```html
  <!-- 옳은 예시 -->
  <html>
    <head>
      <title>제목</title>
    </head>

    <body>
      <p>내용</p>
    </body>
  </html>

  <!-- 잘못된 예시 -->
  <html>
    <head>
      <title>제목
    </head>
      </title>

  </html>
    <body>
      <p>내용
    </body>
      </p>
  ```

- `tag`와 `attribute`는 아무렇게 작성해도 오류가 발생하지 않는다. 다만 브라우저에서 인식하지 못한다.

### Self-closing Tag

- `content` 없이 모든 정보가 `attribute`에 담겨져 있는 태그. 대표적으로 `<img>` 태그가 있으며 아래와 같은 구조로 작성된다.
  ```html
  <br />
  <input type="text" />
  <img src="" alt="" />
  ```

### Semantic-tag (시멘틱 태그)

- 의미를 가진 태그 (`<header>`, `<main>`, `<footer>`, 등)
- 다른 태그를 사용해도(`div`, `span` 등) 같은 기능을 만들 수 있으나 코드의 가독성 혹은 유지보수에 어려움이 생길 수 있는 문제를 방지하기 위해 적극적으로 이용하는 것을 권장한다.
  #### 시멘틱 태그가 중요한 이유
  - 검색 엔진은 해당 콘텐츠를 페이지의 검색 순위에 영향을 미치는 중요한 키워드로 간주한다.
    ([SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO) 참조).
  - 시각 장애가 있는 사용자가 페이지를 탐색하는 데 도움이 되는 이정표로 사용할 수 있다.
  - 의미 있는 코드 블록을 찾는 것이 끝없이 펼쳐진 `div`를 검색하는 것보다 훨씬 쉽다.
  - 개발자에게 태그 안에 채워질 데이터 유형을 제안한다
  - 의미있는 이름짓기(Semantic naming)는 적절한 사용자 정의 요소 / 구성 요소의 이름짓기(namimg)를 반영한다.



### Comment (주석)

- 코드에 영향을 주지 않는 문자열. 코드에 대한 설명이나 메모,의견을 남길 때 사용된다.
- HTML에선 사용자도 읽을 수 있기 때문에 중요한 정보를 남기지 않도록 주의.
  ```html
  <!-- 이런식으로 의견이나 메모를 남겨도 코드에 영향을 주지 않지만 누구나 읽을 수 있다. -->
  <tag attribute="attribute-value">Contents</tag>
  ```