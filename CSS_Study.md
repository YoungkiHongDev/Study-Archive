# CSS
단순한 문서 형태인 HTML을 예쁘게 꾸며주고 구조를 잡아주는 역할을 하는 언어이다.

# CSS 기본 구조
CSS의 기본구조는 다음과 같다.

```css
선택자 {
    속성: 속성값;
}
```

- 선택자: 어떤 HTML 요소를 선택하여 스타일을 적용할 것인지 지정한다.
- 속성: 적용하고자 하는 스타일 종류를 선택한다.
- 속성값: 해당 속성을 어떻게 지정할 것인지 결정한다.

# CSS 적용 방식
CSS 적용 방식에는 크게 3가지가 존재한다.
1. 인라인 방식  
해당 HTML 태그에 직접 style 속성을 추가한다.

```html
<div style="background: red;">인라인 방식 예제</div>
```

2. style 태그 사용  
html 파일의 head 부분 안에 style 태그를 추가하여 사용한다.

```html
<head>
    <style>
        div {
            background: red;
        }
    </style>
</head>
```

3. CSS 파일 분리  
.css 확장자 파일을 따로 만들어서 css를 작성하고, html 파일에서 link 태그로 연결하여 사용한다.

```html
<head>
    <link rel="stylesheet" href="./style.css">
</head>
```

# CSS 기본 선택자
CSS는 선택자로 html의 어디에 적용할 것인지 선택한다. 주로 태그, 아이디, 클래스를 선택자로 사용한다.

1. 태그 선택자  
```css
tag {
    property: value;
}
```

2. 아이디 선택자  
```css
#id {
    property: value;
}
```

3. 클래스 선택자  
```css
.class {
    property: value;
}
```

# CSS 자손 선택자
기본 선택자는 3가지지만, 개발을 진행하면서 구조가 복잡해지면 html 태그 계층으로 부모와 자식이 나눠지는 것을 이용하여, 특정 요소에 css를 적용할 수 있다.

```html
<body>
    <div class="parent">
        <p id="child1">자식 요소1</p>
        <p id="child2">자식 요소2</p>
    </div>
</body>
```
```css
.parent #child2 {
    background: red;
}
```

위와 같이 "공백"으로 선택자를 연결해 사용하면 부모인 div의 자식 중 특정 요소만 css를 적용할 수 있다.