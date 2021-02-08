# scss-masterclass

## 1. FLEXBOX

#### 1.0 Life Before Flexbox

- inline은 box가 아닌 element이다. (너비와 높이가 없음 - 같은 직선에 있음)
- flexbox 이전에 box를 나란히 놓기 위해 사용한 방법 => display:inline-block;

#### 1.1 First Rule of Flexbox

- flexbox에서 box들의 위치를 바꾸고 싶으면 box(children)의 부모를 flex container로 만든다. => display: flex;
- 항상 바로 위에 붙어 있는 부모가 자식을 움직일 수 있다.

#### 1.2 Main Axis and Cross Axis

flex-direction: row일 때(기본 방향), colum은 반대

- 수평축: main axis-가로, 수직축: cross axis-세로
- main axis는 justify-content를 사용하여 item을 움직인다.
- justify-content는 수평축에 있는 flex children의 위치를 변경한다. (property: center, space-between, space-around ...)
- cross axis는 align-items를 사용하여 item을 움직인다.
- align-items는 수직축에 있는 flex children의 위치를 변경한다. (property: center, flex-end, flex-start ...)
