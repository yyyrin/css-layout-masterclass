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

- **`flex-wrap`**
  - `flex-item` 요소들이 강제로 한 줄에 배치되게 할 것인지, 또는 가능한 영역 내에서 벗어나지 않고 여러 행으로 나누어 표현할 것인지 결정하는 속성
  - `flex-wrap: nowrap` : default value, 줄 바꿈 허용X
  - `flex-wrap: wrap` : 줄 바꿈 허용
  - `flex-wrap: wrap-reverse` : 줄 바꿈 + 역순

<br/>

- **`flex-flow`**
  - `flex-direction`, `flex-wrap` 속성의 단축 속성
  - e.g. `flex-flow: row nowrap;` <- default value

<br/><br/>

### 1.4. Align Content

- **`align-content`**
  - 여러 줄로 나뉜 Flexbox 컨테이너에서 각 줄의 간격을 설정함
  - 주로 `flex-wrap: wrap;`과 함께 사용됨
  - Cross Axis에 여분의 공간이 있을 때 flex container의 여러 줄을 정렬함
  - `row-gap`과 `column-gap` 사용하면 유용

<br/><br/>

### 1.5. Order

- **`order`**
  - 자식들에게 `order`를 설정해 줌으로써 자식들의 순서를 바꿀 수 있음
  - `order: 0;` <- defalut value
  - 정렬 순서는 오름차순
- **`align-self`**
  - 자식들이 스스로의 Cross Axis 정렬 설정할 수 있음

<br/><br/>

### 1.6. Flex Grow

- **`flex-grow`**
  - `flex-item` 요소가 `flex-container` 요소 내부에서 할당 가능한 공간의 정도를 선언함
  - 만약 형제 요소로 렌더링된 모든 `flex-item` 요소들이 동일한 `flex-grow` 값을 갖는다면, `flex-container` 내부에서 동일한 공간을 할당받음
  - `flex-grow` 값으로 다른 소수값을 지정한다면, 그에 따라 다른 공간값을 나누어 할당받게 됨

<br/><br/>

### 1.7. Flex Shrink

- **`flex-shrink`**
  - `flex-item` 요소의 크기가 `flex-container` 요소의 크기보다 클 때 `flex-shrink` 속성을 사용
  - 설정된 숫자값에 따라 `flex-container` 요소 내부에서 `flex-item` 요소의 크기가 축소됨
  - `flex-shrink: 0;` : 크기 고정 (축소 X)
  - `flex-shrink: 1;` : default value
  - 숫자 커질수록 더 많이 축소됨
