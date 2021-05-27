# 레이아웃(grid)

2차원의 레이아웃(행, 열) 시스템 제공

flex box도 훌륭하지만 비교적 단순한 1차원 레이아웃을 위하며, 좀 더 복잡한 레이아웃에는 grid사용

flex와 비슷하게 Container와 Item 두가지 개념으로 구분되어 있다.

---

### 사용법(이것만 알면 됨)

1. container로 커다란 틀 만들고(**grid-template-columns/rows사용**, gap사용,grid-auto-row|column도 사용하면 좋고) 
2. item들을 틀에 맞춰서 배치시킨다. (**grid-column, grid-row**)

---

### 속성

#### [container]

- **display**

  값 : grid, inline-grid(inline-flex와 비슷)

- **grid-template** : 행의개수 / 열의개수
  
- **grid-template-rows|columns** : 명시적 행|열의 개수
  
  값 : 1fr(비율), 200px, repeat(3, 1fr)
  
- **grid-template-areas** : items의 grid-area와 연계해서 씀

- **grid-auto-rows|columns** : 암시적 행|열 정의 (새로 생길 행,열들)(음수 사용 불가)

  ex) grid-auto-columns : 1fr;

- **grid-auto-flow**(default:row) : 배치하지 않은 아이템을 어떤 방식의 자동 배치 알고리즘으로 처리할 지 정의

  값 : row, row dense, column, column dense, 

- **grid **: grid-template-xxx 과 grid-auto-xxx의 단축속성

- **gap**

	- **row-gap** : 행 간격
	- **column-gap** : 열 간격

- **place-content** : 각각의 content배치

  - **align-content**: container의 height가 지정이 되어있을 때
  - **justify-content** : container의 width가 지정이 되어있을 때(기본 100%)

- **place-items** : content안의 실제 item의 크기에 따른 지정

  - **align-items**(default:stretch):

    값 : start, center,end, stretch

  - **justify-items**(default:stretch):

    값 : start, center,end, stretch

#### [items]

- **grid-area** : container의 grid-template-areas 와 연계해서 씀(이름 붙여주기)

- **grid-area**: (r-start,c-start,r-end,c-end)
  - **grid-row|column** : 위치 지정 및 길이 늘려줌
    - grid-row|column-start
    - grid-row|column-end
  

- **align-self**
- **justify-self**
- **order**(default:0) : 자동배치 되는 순서 변경(음수 사용 가능)
- **z-index**(default:0): 다른 item과 겹칠때 누가 우선일지 지정

---

### flex-box 대신 grid 쓸 때

1. no-wrap인건 flex-box, wrap인건 grid 쓰고(= 한줄짜리는 flex로 하는게 편하다)
2. flex를 3개이상 겹쳐쓸 때(1~2개로 해결이 안될 때) grid 쓰는게 좋다.

---

### 단위

열(column)을 pixel, percentage, 혹은 ems로 설정시, `fr`로 설정된 것들은 다른 열을 쓰고 남은 공간으로 나뉘어집니다.

ex) grid-template-columns : 1fr 2fr 100px 25% 

​	3번째를 100px쓰고, 4번째를 전체의 25%를 쓰고 남은 부분의 1/3, 2/3이 각각 첫번째,두번째에 부여된다.

---

### 유용한 함수, 변수

- repeat : 1개만 반복이 아니라 (2, 1fr 2fr) 이렇게 여러개 반복도 가능

- span : 확장(item)

	start에 있을때랑 end에 있을때랑 다르다.

	ex) span 3 / 4;  : 4를 기준으로 -3만큼 확장 (=1/4), 1/span 3; : 1을 기준으로 +3만큼 확장(=1/4)

- auto-fill, auto-fit : repeat함수와 같이 쓰이며, grid-template-columns : repeat(auto-fill, minmax(120px,1fr));

  item의 개수가 명확하지 않은 경우에 사용한다.




아래 세개는 grid아니여도 쓸 수 있다.

- fit-content : 행과 열의 크기를 지정하는 속성에 사용 가능, fit-content(내용 최댓값) 하면 내용이 가질 수 있는 크기 최대값을 지정해 주고 그 크기에 아이템 크기를 줄여서 맞춘다.
- min-content : 안에 내용이 가질 수 있는 최솟값(단어단위로)을 그 아이템의 크기로 한다.
- max-content : 안에 내용이 가질 수 있는 최대값을 그 아이템의 크기로 한다.
