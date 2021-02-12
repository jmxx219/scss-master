# scss-masterclass

(S)CSS Layout Master: Flexbox & Grid

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

#### 1.3 align-self and order

father가 아닌 child에게 줄 수 있는 유일한 porperty 2가지.

- align-self는 align-tiem처럼 행동하고 하나의 element에만 설정해도 적용된다.
- 단, father(부모)에게 heigth를 설정해줘야한다.

- order: html을 변경할 필요없이 item의 순서를 변경할 수 있다.
- order는 기본값은 0이다.(값의 오름차순으로 순서가 바뀜)

#### 1.4 wrap, nowrap, reverse, align-content

- flex-wrap: wrap -> flexbox에게 child의 크기를 유지하라고 얘기한다.(child의 width 크기를 유지)
- flex-wrap: nowrap -> 이 element들은 같은 줄에 있어야한다고 flexbox에 얘기한다.(모두 한 줄에 있음)

- flex-direction: row-reverse -> element가 reverse됨(colum은 세로 방향으로)
- 기본값에서 reverse하고 싶다면 flex-wrap: wrap-reverse;

- align-content는 justify-content와 비슷하지만 line을 변경한다.
- align-content: flex-start하면 줄 나눔이 사라진다.

#### 1.5 flex-grow, flex-shrink

child에게 줄 수 있는 property

- flex-shrink는 기본적으로 element의 행동을 정의한다.
- 기본 값은 1이며, 다른 box들 보다 더 넒이가 줄어들게 할 때 사용

- flex-grow는 flex-shrink과 같지만 반대로 작용한다.
- box의 주변 빈공간을 가지면서 커진다.

#### 1.6 flex-basis

child에게 적용되는 property

- element에게 처음 크기를 준다. (실제 크기는 아님)
- flex-basis가 변하지 않으면 flex-basis는 width와 같다.
- flex-shrink와 flex-grow로 크기가 바뀌게 된다.
- flex-direction row일 때, main axis(수평)에서 작용한다.

## 2. GRID

#### 2.1 CSS Grid Basic Concepts

display: grid

- flexbox와 마찬가지로 부모(father)를 grid로 만든다. (규칙은 flexbox와 거의 동일)
- grid-template-columns(rows)로 원하는 column(row)의 개수와 크기를 적어 나눌 수 있다.
- gap으로 column과 row간의 간격을 준다.(gap / column-gap / row-gap)

#### 2.2 Grid Template Areas

- css gird가 가진 함수: repeat(개수, 크기)
- grid-templeate-areas는 layout을 디자인한다. 이때 gird-area로 영역의 이름을 설정해준다.

#### 2.3 Rows and Columns

grid-column-start / grid-column-end => grid-column: start / end
grid-row-start / grid-row-end => grid-row: start / end
grid-column: (시작 라인지점) / span cell개수

- 시작 줄(start)부터 마지막 줄(end)까지 늘린다.
- end가 -1이면 마지막 라인을 뜻한다.

#### 2.4 Line Naming

repeat(2, 100px) => [first-line] 100px [second-line] 100px [third-line];

- line마다 이름을 붙여 사용할 수 있다.

#### 2.5 Grid Template

- fr: fraction(부분)으로 pixel이나 %와 같은 측정 단위이다.
- fr의 개수만큼 grid에서 사용 가능한 공간 크기로 반복한다.
- height를 정해주지 않으면 1fr은 0이 되며, 화면 크기가 달라져도 비율이 똑같다.
- grid-template은 grid-area의 이름을 사용하는데 row의 높이를 구체적으로 정해야한다.
- grid-template에서 repeat는 적용되지 않는다.

#### 2.6 minmax

minmax(최소값, 최대값)

- 얼마나 작게 혹은 크게 element가 될 수 있는지 지정할 수 있다.

#### 2.7 auto-fit, auto-fill

reponsive 디자인

- repeat function에만 사용한다.
- auto-fill은 column이 있는 만큼, 가능한 많이 해당 row를 채운다. 빈 column이 생긴다.
- auto-fit은 현재의 element를 쭉 늘려서 row에 딱 맞게 맞춘다.
