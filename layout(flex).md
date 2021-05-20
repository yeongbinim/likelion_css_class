# flex

flex는 두가지만 이해하면 된다.

1. container, item
2. 중심축,반대축(main axis, cross axis)



## [ container, item ]

**[container]**

- **display**

  값 : flex, grid, block, inline

- **flex-flow**

  - **flex-direction** : 주 축(main-axis)을 설정

    값 : row, row-reverse, column, column-reverse

  - **flex-wrap** : Items의 여러 줄 묶음(줄 바꿈) 설정(default는 한줄로만 item들이 표시된다.)

    값 : nowrap, wrap, wrap-reverse

- **justify-content** : 주 축의 <u>정렬</u> 방법을 설정한다.(default: flex-start)

  값 : flex-start, flex-end, center, space-between*(시작 item은 시작점(flex-start)에, 마지막 item은 끝점(flex-end)에 정렬되고 나머지는 고르게 정렬(**왼쪽 오른쪽 붙어있음**))*, space-around*(Items를 균등한 여백을 포함하여 정렬(**왼쪽 오른쪽에 여백**))*

- **align-content** : 교차 축의 정렬 방법 설정한다.(flex-wrap속성을 통해 item들이 2줄 이상이고 여백이 있을 경우에만 사용가능)(default: stretch)

  값 : stretch(Container의 교차축을 채우기 위해 item들을 늘림), flex-start, flex-end, center, space-between, space-around

- **align-items ** : 교차 축에서 Items의 정렬 방법을 설정한다. align-content와는 달리 한 줄에 대한 정렬방법이기에 여러 줄에서 사용할 때에는 align-content가 우선 적용되므로 align-content는 default(stretch) 가 적용되어야 한다. (default: stretch)

  값 : stretch, flex-start, flex-end, center, baseline(문자열을 기준으로 정렬된다.)



**[items]**

- **order** : Item의 숫서를 설정한다. 숫자가 클수록 순서가 밀린다.(음수 가능)(default:0)

  값 : 숫자

- **flex **

  - **flex-grow** : container가 증가할 때 Item의 증가 너비 비율 설정한다. (이 값이 들어간 것만 증가한다.) (default:0)

    값 : 숫자

    ex ) 1 : 1 : 2 - 맨 왼쪽에 있는건 1/4 크기비율로 늘어난다.

  - **flex-shrink** : container가 감소할 때 Item이 감소 너비 비율 설정(가변 너비가 아니거나 0일 때에는 적용되지 않는다.)(default:1)

    ex) flex-basis : 200px인 상자 2개가 한 줄에 있을 때 container가 90px 줄어든다면 flex-shrink가 2:1 이면 60px, 30px씩 줄어든다.

  - **flex-basis** : 공간 배분 전 기본 너비를 설정 (이것을 기준으로 커질때, 작아질 때가 grow,shrink의 차이다.)(default:0)

    ex1) flex-basis가 auto고, grow가 1일때 기본 너비는 item내부에 들어가 있는 content의 너비로 계산되고, grow 비율은 나머지 영역의 비율이다.

    ex2) flex-basis가 0이고, grow가 1 일 때 그냥 item기준으로 비율 조정(가장 많이 쓸듯)

    ex3) flex-basis가 100이고, grow가 1 일 때 grow의 비율은 나머지 영역의 비율이다. ( 안 헷갈리게 flex-basis가 auto안되게 하는건 필수일듯)

- **align-self** : container에서 쓸 수 있는 align-items와 비슷하지만 이것은 이 아이템만 적용이 되고, 당연히 align-items보다 우선시 된다. (default: auto(align-items의 속성을 상속받음))

  값 : auto, stretch, flex-start, flex-end, center, baseline



## [ 중심축(주축) ,반대축(교차축) (main axis, cross axis) ]

- 주축, 교차축

  { flex-direction : row } 라면 수평이 주축이 되고 수직이 교차축이 된다.

  column이라면 수평이 교차축, 수직이 주축이 된다.

- 시작점과(flex-start) 끝점(flex-end)

  { flex-direction : row } 라면 시작점이 왼쪽, row-reverse라면 시작점이 오른쪽이다.

  column이라면 시작점이 위쪽, column-reverse라면 시작점이 아래쪽이다.
