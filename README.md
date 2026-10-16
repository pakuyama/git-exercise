# 마크다운(Markdown) 사용법

> 참고: [ihoneymon - 마크다운 사용법](https://gist.github.com/ihoneymon/652be052a0727ad59601)

---

## 1. 마크다운이란?

마크다운(Markdown)은 텍스트 기반의 가벼운 마크업 언어입니다.
2004년 존 그루버(John Gruber)가 만들었고, 쉽게 쓰고 읽을 수 있으며 HTML로 변환할 수 있습니다.
GitHub의 `README.md` 파일이 대표적인 예입니다.

### 1.1 장점

1. 문법이 간결하다.
2. 별도의 도구 없이 메모장으로도 작성할 수 있다.
3. 다양한 형태로 변환할 수 있다.
4. 텍스트 파일이라 용량이 작고 보관하기 쉽다.
5. 텍스트이므로 Git 같은 버전 관리 시스템으로 변경 이력을 관리할 수 있다.
6. 지원하는 프로그램과 플랫폼이 많다.

### 1.2 단점

1. 표준이 하나로 정해져 있지 않다.
2. 도구마다 변환 결과가 조금씩 다르다.
3. 모든 HTML 마크업을 대신할 수는 없다.

---

## 2. 마크다운 문법

### 2.1 헤더(Header)

* 큰 제목: 아래에 `=`를 붙인다. (`<h1>`)

```
큰 제목
=======
```

* 작은 제목: 아래에 `-`를 붙인다. (`<h2>`)

```
작은 제목
---------
```

* 글머리: `#`의 개수로 1~6단계까지 지원한다. (7단계는 지원하지 않음)

```
# h1
## h2
### h3
#### h4
##### h5
###### h6
```

### 2.2 인용문(BlockQuote)

`>`를 사용하며, 중첩할 수 있습니다.

```
> 첫 번째 인용문
>> 두 번째 인용문
>>> 세 번째 인용문
```

> 첫 번째 인용문
>> 두 번째 인용문
>>> 세 번째 인용문

인용문 안에서 다른 마크다운 요소도 사용할 수 있습니다.

> ### 인용문 안의 제목
> * 목록
>
> ```
> 코드
> ```

### 2.3 목록(List)

#### 순서 있는 목록

숫자와 점을 사용합니다. 숫자를 어떤 순서로 적든 앞에서부터 차례대로 번호가 매겨집니다.

```
1. 첫 번째
3. 세 번째
2. 두 번째
```

1. 첫 번째
3. 세 번째
2. 두 번째

#### 순서 없는 목록

`*`, `+`, `-`를 사용하며, 섞어서 중첩할 수도 있습니다.

```
* 1단계
  - 2단계
    + 3단계
      + 4단계
```

* 1단계
  - 2단계
    + 3단계
      + 4단계

### 2.4 코드(Code)

#### 들여쓰기

스페이스 4개 또는 탭 1개로 들여쓰면 코드 블록이 됩니다. 앞뒤로 빈 줄이 한 줄씩 있어야 합니다.

```
일반 문단입니다.

    코드 블록입니다.

코드 블록이 끝났습니다.
```

일반 문단입니다.

    코드 블록입니다.

코드 블록이 끝났습니다.

#### 코드 블록 태그

`<pre><code>` 태그로 감싸도 코드 블록이 됩니다.

```html
<pre>
<code>
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
</code>
</pre>
```

#### 코드 펜스(GitHub)

백틱 3개(```` ``` ````)로 감싸고, 여는 백틱 뒤에 언어 이름을 적으면 문법 강조(syntax highlighting)가 적용됩니다.

````
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
````

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

문장 안의 짧은 코드는 백틱 1개로 감쌉니다: `git status`

### 2.5 수평선(Horizontal Rule)

아래 중 어느 것을 써도 수평선 `<hr/>`이 됩니다. 페이지를 나눌 때 씁니다.

```
* * *
***
*****
- - -
---------------------------------------
```

---

### 2.6 링크(Link)

* 참조 링크

```
[구글][google]

[google]: https://www.google.com "Go google"
```

[구글][google]

[google]: https://www.google.com "Go google"

* 인라인 링크

```
[구글](https://www.google.com)
```

[구글](https://www.google.com)

* 자동 연결

```
<https://www.google.com>
<example@example.com>
```

<https://www.google.com>

### 2.7 강조(Emphasis)

```
*기울임* 또는 _기울임_
**굵게** 또는 __굵게__
~~취소선~~
```

*기울임* 또는 _기울임_  
**굵게** 또는 __굵게__  
~~취소선~~

### 2.8 이미지(Image)

```
![대체 텍스트](이미지경로 "선택적 제목")
```

마크다운 문법만으로는 이미지 크기를 정할 수 없으므로, 크기를 지정하려면 HTML `<img>` 태그를 씁니다.

```html
<img src="이미지경로" width="300px" height="200px" alt="설명"></img>
```

### 2.9 줄바꿈(Line Break)

줄 끝에 스페이스를 2개 이상 넣으면 줄이 바뀝니다. 그냥 엔터만 치면 한 줄로 이어집니다.

```
첫 번째 줄입니다.(스페이스 2개)  
두 번째 줄입니다.
```

첫 번째 줄입니다.  
두 번째 줄입니다.

---

## 3. 마무리

마크다운은 문법이 간단해서 문서를 빠르게 작성하고, 어디서든 같은 형태로 볼 수 있습니다.
더 자세한 문법은 [Markdown Guide](https://www.markdownguide.org/)에서 확인할 수 있습니다.

## 참고

* [ihoneymon - 마크다운 사용법 (Gist)](https://gist.github.com/ihoneymon/652be052a0727ad59601)
* [John Gruber - Markdown](https://daringfireball.net/projects/markdown/)
* [GitHub Docs - 기본 서식 구문](https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
