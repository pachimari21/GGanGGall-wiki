# 위키 페이지 서식 작성 가이드

Retype은 마크다운을 사용하여 웹사이트를 쉽게 만들 수 있는 도구. 이 가이드는 Retype에서 사용 가능한 다양한 서식 요소 소개.

## 목차
- [기본 마크다운 문법](#기본-마크다운-문법)
- [Retype 특수 기능](#retype-특수-기능)
- [컴포넌트 요소](#컴포넌트-요소)
- [페이지 구성 및 네비게이션](#페이지-구성-및-네비게이션)
- [검색 최적화](#검색-최적화)

---

## 기본 마크다운 문법

### 제목

```markdown
# 제목 1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
###### 제목 6
```

### 텍스트 서식

```markdown
**굵게** 또는 __굵게__
*기울임꼴* 또는 _기울임꼴_
~~취소선~~
`인라인 코드`
```

출력:
**굵게** 또는 __굵게__
*기울임꼴* 또는 _기울임꼴_
~~취소선~~
`인라인 코드`

### 링크

```markdown
[링크 텍스트](https://example.com)
[내부 페이지 링크](../another-page.md)
[같은 페이지 내 링크](#제목-1)
```

### 이미지

```markdown
![대체 텍스트](이미지경로.jpg)
![대체 텍스트](이미지경로.jpg "이미지 제목")
```

### 목록

순서 없는 목록:
```markdown
- 항목 1
- 항목 2
  - 하위 항목 1
  - 하위 항목 2
- 항목 3
```

순서 있는 목록:
```markdown
1. 첫 번째 항목
2. 두 번째 항목
3. 세 번째 항목
```

### 인용문

```markdown
> 이것은 인용문입니다.
> 
> 여러 줄에 걸쳐 작성할 수 있습니다.
```

출력:
> 이것은 인용문입니다.
> 
> 여러 줄에 걸쳐 작성할 수 있습니다.

### 코드 블록

````markdown
```javascript
function hello() {
  console.log("Hello, world!");
}
```
````

출력:
```javascript
function hello() {
  console.log("Hello, world!");
}
```

### 표

```markdown
| 열 1 | 열 2 | 열 3 |
|------|------|------|
| 행 1 | 데이터 | 데이터 |
| 행 2 | 데이터 | 데이터 |
```

출력:
| 열 1 | 열 2 | 열 3 |
|------|------|------|
| 행 1 | 데이터 | 데이터 |
| 행 2 | 데이터 | 데이터 |

### 수평선

```markdown
---
```

---

## Retype 특수 기능

### 페이지 설정

각 마크다운 파일 상단에 YAML 프론트매터를 추가하여 페이지 설정을 지정할 수 있다:

```yaml
---
label: 사이드바에 표시될 라벨
icon: :star: # 이모지 또는 아이콘 이름
order: 100 # 사이드바에서의 순서
tags: [태그1, 태그2]
description: 페이지 설명
---
```

### 탭 컴포넌트

Retype의 탭 기능:

```markdown
+++ 탭1
첫 번째 탭 내용.
+++ 탭2
두 번째 탭 내용.
+++
```

출력 예시:

+++ 탭1
첫 번째 탭 내용.
+++ 탭2
두 번째 탭 내용.
+++

### 패널 / 알림

```markdown
!!! 정보
정보를 담은 패널.
!!!

!!! 경고
경고 메시지를 담은 패널.
!!!

!!! 성공
성공 메시지를 담은 패널.
!!!
```

출력 예시:

!!! 정보
정보를 담은 패널.
!!!

!!! 경고
경고 메시지를 담은 패널.
!!!

!!! 성공
성공 메시지를 담은 패널.
!!!

### 아코디언 (확장/축소 가능한 섹션)

```markdown
||| 제목을 클릭하여 펼치기
숨겨진 내용.
|||
```

출력 예시:

||| 제목을 클릭하여 펼치기
숨겨진 내용.
|||

## 컴포넌트 요소

### 버튼

```markdown
[!button 버튼 텍스트](https://example.com)
```

출력 예시:

[!button 버튼 텍스트](https://example.com)

### 뱃지

```markdown
:badge[NEW]
:badge[중요]{color="red"}
```

출력 예시:

:badge[NEW]
:badge[중요]{color="red"}

### 코드 블록 기능

단순 코드 블록:

````markdown
```html
<div>
  <p>Hello World</p>
</div>
```
````

Retype에서는 코드 복사 버튼이 자동으로 추가된다.

### 파일 이름 및 라인 강조

코드 블록에 파일 이름 추가:

````markdown
```js name="script.js"
function hello() {
  return "Hello, World!";
}
```
````

라인 강조:

````markdown
```js highlight="2"
function hello() {
  return "Hello, World!";
}
```
````

## 페이지 구성 및 네비게이션

### 목차 설정

프론트매터에 목차 설정을 추가할 수 있다:

```yaml
---
toc:
  depth: 3  # 목차에 포함할 제목 레벨의 깊이
  minHeadingLevel: 2  # 목차에 포함할 최소 제목 레벨
  maxHeadingLevel: 4  # 목차에 포함할 최대 제목 레벨
---
```

### 카테고리 만들기

폴더 이름을 이용해 카테고리를 만들 수 있습니다. 각 폴더에 `readme.md` 파일을 추가하여 카테고리 소개 페이지를 작성할 수 있다:

```
docs/
  category1/
    readme.md  # 카테고리 소개 페이지
    page1.md
    page2.md
  category2/
    readme.md
    another-page.md
```

### 숨겨진 페이지

프론트매터에 `visibility: hidden`을 추가하여 페이지를 사이드바에서 숨길 수 있다:

```yaml
---
visibility: hidden
---
```

## 검색 최적화

### 메타데이터 추가

검색 엔진 최적화를 위해 메타데이터를 추가할 수 있다:

```yaml
---
title: 페이지 제목
description: 페이지에 대한 자세한 설명
author: 작성자 이름
category: 페이지 카테고리
tags: [태그1, 태그2, 태그3]
---
```

### 검색어 설정

특정 검색어와 연결하려면 다음과 같이 설정한다:

```yaml
---
search:
  boost: 2  # 검색 결과에서 이 페이지의 중요도 (기본값: 1)
  keywords: [검색어1, 검색어2]
---
```

## retype.yml 설정

전체 사이트 설정을 위한 `retype.yml` 파일 예시:

```yaml
input: .
output: .retype
url: https://example.com/docs

branding:
  title: 문서 사이트명
  label: v1.0
  logo: /static/logo.png

links:
  - text: 홈페이지
    link: https://example.com
  - text: GitHub
    link: https://github.com/username/repo

footer:
  copyright: "© Copyright {{ year }}. All rights reserved."

poweredByRetype: true  # Retype 브랜딩 표시 여부
```

---

이 가이드로 Retype의 다양한 서식 요소와 기능을 활용해 문서 사이트 제작 가능.

[!button variant="primary" icon="rocket" text="Retype 공식 문서"](https://retype.com/)
