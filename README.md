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
