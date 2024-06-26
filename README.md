# CSS Layout Masterclass

## 1. Flexbox

### 1.1. Before Flexbox

- `.box` -> `<div class="box"></div>`
- `#box` -> `<div id="box"></div>`
- `div.box*3` ->
  `<div class="box"></div>`
  `<div class="box"></div>`
  `<div class="box"></div>`

<br/>

- HTML 요소의 3가지 배치 방식
  - `display: inline` : 바로 옆에 다른 요소 올 수 있음. 크기 지정 못함
  - `display: block` : 옆에 다른 요소 올 수 없음. 다음 줄로 넘어감. 크기 지정 가능.
  - `display: inline-block` : 옆에 다른 요소가 올 수 있으면서 크기 지정도 가능.

<br/>

- `flexbox`가 등장하게 된 이유
  - 박스를 왼쪽, 중간, 오른쪽으로 배치하고 싶을 때, 픽셀 혹은 %를 일일히 조정해야 하는 번거로움 + 기기마다 다른 화면 너비 (레이아웃 틀어짐)

<br/><br/>

### 1.2. Main and Cross Axis

- `flex-direction`이 `row`로 설정된 경우(기본값), **Main Axis**는 왼쪽에서 오른쪽으로 수평으로 향하고, **Cross Axis**는 위에서 아래로 수직으로 향함
- `flex-direction`이 `column`으로 설정된 경우, **Main Axis**는 위에서 아래로 수직으로 향하고, **Cross Axis**는 왼쪽에서 오른쪽으로 수평으로 향함
- `justify-content`는 flex container의 Main Axis를 따라 아이템을 정렬함
- `align-items`는 flex container의 Cross Axis를 따라 아이템을 정렬함

<br/><br/>

### 1.3. Flex Flow

#### `flex-wrap`

- `flex-item` 요소들이 강제로 한 줄에 배치되게 할 것인지, 또는 가능한 영역 내에서 벗어나지 않고 여러 행으로 나누어 표현할 것인지 결정하는 속성
- `flex-wrap: nowrap` : default value, 줄 바꿈 허용X
- `flex-wrap: wrap` : 줄 바꿈 허용
- `flex-wrap: wrap-reverse` : 줄 바꿈 + 역순

<br/>

#### `flex-flow`

- `flex-direction`, `flex-wrap` 속성의 단축 속성
- e.g. `flex-flow: row nowrap;` <- default value

<br/><br/>

### 1.4. Align Content

#### `align-content`

- 여러 줄로 나뉜 Flexbox 컨테이너에서 각 줄의 간격을 설정함
- 주로 `flex-wrap: wrap;`과 함께 사용됨
- Cross Axis에 여분의 공간이 있을 때 flex container의 여러 줄을 정렬함
- `row-gap`과 `column-gap` 사용하면 유용

<br/><br/>

### 1.5. Order

#### `order`

- 자식들에게 `order`를 설정해 줌으로써 자식들의 순서를 바꿀 수 있음
- `order: 0;` <- defalut value
- 정렬 순서는 오름차순

<br/>

#### `align-self`

- 자식들이 스스로의 Cross Axis 정렬 설정할 수 있음

<br/><br/>

### 1.6. Flex Grow

#### `flex-grow`

- `flex-item` 요소가 `flex-container` 요소 내부에서 할당 가능한 공간의 정도를 선언함
- 만약 형제 요소로 렌더링된 모든 `flex-item` 요소들이 동일한 `flex-grow` 값을 갖는다면, `flex-container` 내부에서 동일한 공간을 할당받음
- `flex-grow` 값으로 다른 소수값을 지정한다면, 그에 따라 다른 공간값을 나누어 할당받게 됨
- `flex-grow: 0;`: `flex-item`이 여유 공간 차지X (default value)
- `flex-grow` 값을 1이상의 값으로 설정하면 해당 `flex-item`은 여유 공간을 더 많이 차지

<br/><br/>

### 1.7. Flex Shrink

#### `flex-shrink`

- `flex-item` 요소의 크기가 `flex-container` 요소의 크기보다 클 때 `flex-shrink` 속성을 사용
- 설정된 숫자값에 따라 `flex-container` 요소 내부에서 `flex-item` 요소의 크기가 축소됨
- `flex-shrink: 0;` : 축소X , 자신의 본래 크기 유지
- `flex-shrink: 1;` : 필요에 따라 축소될 수 있음 (default value)
- 숫자 커질수록 더 많이 축소됨

<br/><br/>

### 1.8. Flex Basis

#### `flex-basis`

- `flex-grow`로 커지기 시작하는 지점이자, `flex-shrink`로 줄어들기 시작하는 지점
- 커지거나 줄어들기 전의 초기 **길이**
  - 초기 너비가 아닌 **길이**인 이유는 Main Axis를 따라가기 때문에 `flex-direction`이 `column`인 경우 `height`가 되기 때문
  - 즉, `width`와 다른 점은 Main Axis를 기준으로 한다는 점
- e.g. `flex-grow: 2;` `flex-shrink: 0;`와 함께 사용 시, `flex-basis`는 `min-width`와 같은 효과 낼 수 있음
- e.g. `flex-grow: 0;` `flex-shrink: 5;`와 함께 사용 시, `flex-basis`는 `max-width`와 같은 효과 낼 수 있음

<br/>

#### `flex: flex-grow flex-shrink flex-basis;`

- `flex-grow`와 `flex-shrink`, `flex-basis`를 한 번에 작성 가능

<br/><br/>

## 2. Grid

### 2.1. Columns and Rows

#### `grid-template-columns`

#### `grid-template-rows`

<br/>

- `container`에서 Gird 트랙의 크기들을 지정해주는 속성
- 여러가지 단위를 사용할 수 있고 섞어서 사용 가능

  ```css
  .container {
    grid-template-columns: 200px 200px 500px;
    /* grid-template-columns: 1fr 1fr 1fr */
    /* grid-template-columns: repeat(3, 1fr) */
    /* grid-template-columns: 200px 1fr */
    /* grid-template-columns: 100px 200px auto */

    grid-template-rows: 200px 200px 500px;
    /* grid-template-rows: 1fr 1fr 1fr */
    /* grid-template-rows: repeat(3, 1fr) */
    /* grid-template-rows: 200px 1fr */
    /* grid-template-rows: 100px 200px auto */
  }
  ```

<br/>

- `grid-template-columns: 200px 200px 500px;`
  - column을 `200px`, `200px`, `500px`로 만듦
- `grid-template-columns: 1fr 1fr 1fr;`
  - `fr`: fraction(여기로)을 의미하며, 숫자 비율대로 트랙의 크기 나눔
  - `1fr 1fr 1fr`: 균일하게 1:1:1 비율인 3개의 column 만듦
- 고정 크기와 가변 크기 섞어서 사용 가능
  - `grid-template-columns: 100px 2fr 1fr;`

<br/><br/>

### 2.2. Grid Lines

#### `grid-column-start`

#### `grid-column-end`

#### `grid-column`

#### `grid-row-start`

#### `grid-row-end`

#### `grid-row`

<br/>

- Grid **아이템**에 적용하는 속성으로, 각 셀의 영역을 지정함
- `grid-column-start`가 시작 번호, `grid-column-end`가 끝 번호
- `grid-column`: start와 end 속성을 한번에 쓰는 축약형

```css
.item:nth-child(1) {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 2;
}
```

```css
/* 위와 동일한 결과 */
.item:nth-child(1) {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

<br/><br/>

### 2.3. Line Names

- line의 이름을 적용시킬 때 반드시 +1개 만들기
  - `grid-template-rows`가 3개인 경우, 4개로 지정한 rows를 감싸는 형식

```css
.father {
  display: grid;
  grid-template-columns: [cucumber] 100px [potato] 200px [banana] 50px [brocoli];
  grid-template-rows: [korea] 200px [thailand] 100px [greece];
}

.child:last-child {
  grid-column: potato / brocoli;
}

.child:first-child {
  grid-row: korea / greece;
}
```

```css
/* 위와 동일한 결과 */
.child:last-child {
  grid-column: 2 / -1;
}

.child:first-child {
  grid-row: 1 / -1;
}
```

<br/><br/>

### 2.4. Grid Template

#### `grid-template-areas`

#### `grid-template`

#### `grid-area`

- 각 영역(Grid Area)에 이름을 붙이고, 그 이름을 이용해 배치하는 방법

  ```css
  .container {
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 2fr 1fr;
    grid-template-areas:
      "a a a a"
      "b b b c"
      "d d d d";
  }
  ```

  - 각자 차지하는 셀의 개수만큼 해당 위치에 이름 작성
  - 각 셀마다 공백을 하나씩 넣어서 구분
  - `a`는 첫 번째 row에서 4개의 column을 차지하니 맨 위에 4번 작성
  - 빈 칸은 마침표 또는 `"none"` 사용

  ```css
  /* 위와 동일한 결과 */
  .container {
    grid-template:
      "a a a a" 1fr
      "b b b c" 2fr
      "d d d d" 1fr / 1fr 1fr 1fr 1fr;
  }
  ```

<br/>

- **해당 아이템** 요소에 **`grid-area`** 속성으로 이름 지정하면 각 영역의 이름 매칭

  ```css
  /* 이름 값에 따옴표 없음 주의 */
  header {
    grid-area: a;
  }

  section {
    grid-area: b;
  }

  aside {
    grid-area: c;
  }

  footer {
    grid-area: d;
  }
  ```

<br/><br/>

### 2.5. The Span Keyword

#### `span`

- **몇 개의 셀을 차지하게 할 건지** 지정
  ```css
  .item:nth-child(1) {
    /* 1번 라인에서 시작해서 2칸 차지 */
    grid-column: 1 / span 2;
    /* 1번 라인에서 시작해서 3칸 차지 */
    grid-row: 1 / span 3;
  }
  ```

<br/><br/>

### 2.6. Auto Columns and Rows

#### `grid-auto-rows`

#### `grid-auto-columns`

- 통제를 벗어난 위치에 있는 트랙의 크기를 지정하는 속성
- row나 column의 개수를 미리 알 수 없는 경우 사용
- `grid-template-rows`로 미리 세팅해 둔 것이 없을 때, 모든 row는 `grid-tempalte-rows`의 통제를 벗어난 row가 됨
  - 이를 `grid-auto-rows`가 처리

```css
.father {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  /* 3번째 row부터 1fr */
  grid-auto-rows: 1fr;
  /* 3번째 column부터 0.5fr */
  grid-auto-columns: 0.5fr;
}
```

<br/>

#### `grid-auto-flow`

- 아이템이 자동 배치되는 흐름을 결정하는 속성
- row 또는 column을 따라 배치하거나 빈 공간을 최소화하여 배치 가능
- `grid-auto-flow: row;`: default value
- `column`: 그리드 아이템이 열을 따라 배치
- `dense`: 빈 공간을 최소화하여 가능한 모든 아이템을 배치
- `row dense`: 행 방향으로 빈 공간을 최소화하여 배치
- `column dense`: 열 방향으로 빈 공간을 최소화하여 배치

<br/><br/>

### 2.7. Align and Justify items

- `stretch`
  - default value
  - 아이템의 width나 height가 없다면 셀의 처음부터 끝까지 차지

#### `justify-items`

- 아이템들을 가로(row축) 방향으로 정렬

  ```css
  .container {
    justify-items: stretch;
    /* justify-items: start; */
    /* justify-items: center; */
    /* justify-items: end; */
  }
  ```

<br/>

#### `align-items`

- 아이템들을 세로(column축) 방향으로 정렬

  ```css
  .container {
    align-items: stretch;
    /* align-items: start; */
    /* align-items: center; */
    /* align-items: end; */
  }
  ```

<br/>

#### `place-items`

- `align-items`와 `justify-items`를 같이 쓸 수 있는 단축 속성
- `align-items`, `justify-items`의 순서로 작성
- 하나의 값만 쓰면 두 속성 모두에 적용됨

  ```css
  .container {
    place-items: center start;
  }
  ```

<br/>

#### `align-self`

- 해당 아이템을 세로(column축) 방향으로 정렬

  ```css
  .item {
    align-self: stretch;
    /* align-self: start; */
    /* align-self: center; */
    /* align-self: end; */
  }
  ```

<br/>

#### `justify-self`

- 해당 아이템을 가로(row축) 방향으로 정렬

  ```css
  .item {
    justify-self: stretch;
    /* justify-self: start; */
    /* justify-self: center; */
    /* justify-self: end; */
  }
  ```

<br/>

#### `place-self`

- `place-self`와 `justify-self`를 같이 쓸 수 있는 단축 속성
- `align-self`, `justify-self` 순서로 작성
- 하나의 값만 쓰면 두 속성 모두에 적용됨

  ```css
  .item {
    place-self: start center;
  }
  ```

<br/><br/>

### 2.8. Align and Justify Content

#### `align-content`

- Grid 아이템들의 높이를 모두 합 한 값이 Grid 컨테이너의 높이보다 작을 때 Grid 아이템들을 통째로 정렬함

  ```css
  .container {
    align-content: stretch;
    /* align-content: start; */
    /* align-content: center; */
    /* align-content: end; */
    /* align-content: space-between; */
    /* align-content: space-around; */
    /* align-content: space-evenly; */
  }
  ```

<br/>

#### `justify-content`

- Grid 아이템들의 너비를 모두 합한 값이 Grid 컨테이너의 너비보다 작을 때 Grid 아이템들을 통째로 정렬

  ```css
  .container {
    justify-content: stretch;
    /* justify-content: start; */
    /* justify-content: center; */
    /* justify-content: end; */
    /* justify-content: space-between; */
    /* justify-content: space-around; */
    /* justify-content: space-evenly; */
  }
  ```

<br/>

#### `place-content`

- `align-content`와 `justify-content`를 같이 쓸 수 있는 단축 속성
- `align-content`, `justify-content`의 순서로 작성
- 하나의 값만 쓰면 두 속성 모두에 적용됨

  ```css
  .container {
    place-content: space-between center;
  }
  ```

<br/>

- `items` -> item을 어떻게 배치할 것인가에 대한 속성
- `content` -> item의 줄 간격을 어떻게 배치할 것인가에 대한 속성

<br/><br/>

### 2.9. Auto Sizing and Minmax

#### `min-content`

- Grid 아이템이 포함하는 내용(Contents)의 최소 크기
- 아이템이 텍스트인 경우, 가장 긴 단어가 기준이 됨

  ```css
  .container {
    grid-template-columns: 1fr min-content 1fr;
  }
  ```

<br/>

#### `max-content`

- Grid 아이템이 포함하는 내용(Contents)의 최대 크기
- 아이템이 텍스트인 경우, 길이가 길더라도 줄바꿈 없이 한 줄로 보여줌

  ```css
  .container {
    grid-template-columns: 1fr max-content 1fr;
  }
  ```

<br/>

#### `minmax()`

- 최솟값과 최댓값을 지정할 수 있는 함수
- **`minmax(100px, auto)`**: **최소한 100px, 최대는 자동으로(auto) 늘어나게**
- 아무리 내용의 양이 적더라도 최소한 높이 100px은 확보하고, 내용이 많아 100px이 넘어가면 알아서 늘어나도록 처리해준 예시

  ```css
  .container {
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, minmax(100px, auto));
  }
  ```

<br/><br/>

### 2.10. Auto Fill and Auto Fit

#### `auto-fill`

#### `auto-fit`

- column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채움
- `auto-fill`: 최대한 많은 아이템을 배치하고, 남은 공간은 비어있게 함
- `auto-fit`: 필요한 만큼의 아이템을 배치하고, 남은 공간은 아이템을 늘려 채움

  ```css
  .father {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    /* grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); */
  }
  ```

<br/><br/>

## 3. SCSS

### 3.1. Introduction

- Sass(SCSS): 코드의 재활용성을 올리고, 가독성을 올리는 등 CSS에서 보이던 단점을 보완하고, 개발의 효율을 올리기 위해 등장한 **CSS 전처리기 언어**
- 웹은 CSS밖에 모르기 때문에, 우선 전처리기 언어 문법으로 코딩하고, CSS로 **컴파일**해서 웹에서 동작시킴

<br/>

- Vite 환경에서 SCSS 설치

  ```bash
  npm add -D sass
  ```

<br/>

- 변수 설정 및 사용

  ```scss
  <!-- SCSS에서 변수 사용 방식 -->
  $bgColor: red;

  body {
    background-color: $bgColor;
  }
  ```

  ```css
  <!-- 기존 CSS에서 변수 사용 방식 -- > :root {
    --bgColor: red;
  }

  body {
    background-color: var(--bgColor);
  }
  ```

<br/><br/>

### 3.2. Nesting

- 선택자의 중첩(Nesting)을 통해 반복되는 부모요소 선택자 사용을 줄일 수 있음

  ```css
  ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    gap: 10px;
  }

  ul li {
    background-color: tomato;
    color: white;
    padding: 5px 10px;
    border-radius: 7px;
  }
  ```

  ```scss
  ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    gap: 10px;

    li {
      background-color: tomato;
      color: white;
      padding: 5px 10px;
      border-radius: 7px;
    }
  }
  ```

<br/><br/>

### 3.3. @extend

- 상속되는 선택자를 계층적으로 명시하여 불필요한 반복적 사용을 줄일 수 있음

  ```scss
  %alert {
    margin: 10px;
    padding: 10px 20px;
    border-radius: 10px;
    border: 1px dashed black;
  }

  .success {
    @extend %alert;
    background-color: green;
  }

  .error {
    @extend %alert;
    background-color: tomato;
  }
  ```

<br/><br/>

### 3.4. Mixins

- 프로그래밍 언어에서 사용하는 조건문, 반복문을 통해서 동적으로 CSS 관리 가능
- JavaScript의 function과 같은 코드 덩어리를 만들고, function(`@mixin`으로 만들어진 코드 덩어리)이 argument(인자)를 받을 수 있게 함
- `@include`를 사용하여 argument(인자)를 보내고, function을 불러옴
- 인자는 여러 개 가능

  ```SCSS
  @mixin alert($bgColor, $borderColor) {
    background-color: $bgColor;
    margin: 10px;
    padding: 10px 20px;
    border-radius: 10px;
    border: 1px dashed $borderColor;
  }

  .success {
    @include alert(green, blue);
  }

  .error {
    @include alert(tomato, white);
  }

  .warning {
    @include alert(yellow, black);
  }
  ```

<br/><br/>

### 3.5. Responsive Mixins

- SCSS에서 반응형 사이즈 사용법

```SCSS
$breakpoint-sm: 480px;
$breakpoint-md: 768px;
$breakpoint-lg: 1024px;
$breakpoint-xl: 1200px;

@mixin smallDevice {
  @media screen and (min-width: $breakpoint-sm) {
    @content;
  }
}

@mixin mediumDevice {
  @media screen and (min-width: $breakpoint-md) {
    @content;
  }
}

@mixin largeDevice {
  @media screen and (min-width: $breakpoint-lg) {
    @content;
  }
}

@mixin xlDevice {
  @media screen and (min-width: $breakpoint-xl) {
    @content;
  }
}

body {
  @include smallDevice {
    background-color: blue;
  }

  @include mediumDevice {
    background-color: red;
  }

  @include largeDevice {
    background-color: purple;
  }

  @include xlDevice {
    background-color: pink;
  }
}
```

<br/><br/>

## 4. 기타

### 4.1. Box Sizing

- 요소의 너비와 높이를 계산하는 방법을 지정하는 속성
- `content-box`
  - default value
  - 설정한 `width`와 `height;` 값이 곧 **요소 내부의 콘텐츠 크기**
- `border-box`
  - 설정한 `width`와 `height` 값이 **안쪽 여백과 테두리까지 포함**

<br/>

### 4.2. Width

- 기본값은 콘텐츠 영역의 너비이지만, `box-sizing`이 `border-box`라면 테두리 영역의 너비를 설정함
- `max-content`
  - 요소의 자식 요소들이 차지하는 최대 너비만큼 요소의 너비 설정
- `min-content`
  - 요소의 자식 요소들이 차지하는 최소 너비만큼 요소의 너비 설정
- `fit-content`
  - 요소의 너비가 콘텐츠의 크기와 부모 요소의 크기 사이에서 적절한 값을 가지도록 설정

<br/>

### 4.3. Overflow

- 요소의 콘텐츠가 너무 커서 요소의 블록 서식 맥락에 맞출 수 없을 때의 처리법 지정
- `visible`
  - default value
  - 넘치는 콘텐츠가 잘리지 않고 표시됨
- `hidden`
  - 넘치는 콘텐츠가 잘리고, 스크롤바가 표시되지 않음
- `scroll`
  - 넘치는 콘텐츠가 잘리고, 항상 스크롤바가 표시됨
- `auto`
  - 넘치는 콘텐츠가 있을 때만 스크롤바가 표시됨

<br/>

### 4.4. `<img>` 태그 vs. `background-image` 속성

#### `<img>` 태그

- 장점
  - **SEO 친화적**
    - 이미지에 `alt` 속성을 추가하여 검색 엔진에 이미지의 내용 설명할 수 있음
    - 이미지에 대한 접근성 향상
  - **쉬운 이미지 삽입**
    - 단순히 태그 하나로 이미지 삽입 가능
    - 크기 조정 및 다른 HTML 속성 쉽게 추가 가능
  - **이미지 고유 컨텐츠 역할**
    - 이미지를 독립적인 컨텐츠로 취급할 때 유용
    - HTML 문서에서 이미지의 위치를 명확하게 지정 가능
- 단점
  - **유연성 부족**
    - 스타일링 및 위치 지정에 제한 있을 수 있음
    - 배경 이미지로 사용하기에는 부적절

#### `background-image` 속성

- 장점
  - **디자인 유연성**
    - CSS를 이용해 다양한 스타일 적용 가능 (반복, 위치 조정, 크기 조정 등)
    - 여러 배경 이미지를 한 요소에 적용 가능
  - **레이아웃에 유리**
    - 배경 이미지로 사용되어야 할 경우 유리
    - 이미지가 텍스트나 다른 요소 뒤에 위치할 수 있음
  - **반응형 디자인**
    - 미디어 쿼리를 통해 다양한 화면 크기에 맞게 조정 가능
- 단점
  - **SEO 비친화적**
    - 검색 엔진이 배경 이미지를 인식 못함
    - 접근성 문제 발생 가능
  - **추가적인 코드 필요**
    - CSS를 별도로 작성해야 함
    - HTML과 CSS 파일이 분리되어 관리 복잡성 증가

#### 결론

- **컨텐츠 이미지** : `<img>` 태그 사용
- **디자인 요소** : `background-image` 속성 사용

<br/>

### 4.5. `border` 대체하는 방법

- 부모 요소의 `background-color`를 `border`의 color로 설정
- 자식 요소의 `background-color`를 원하는 색으로 설정
- 부모 요소에 `gap` 속성을 사용하여 자식 요소와의 간격 설정
  - 이 간격이 `border`처럼 보이게 됨
