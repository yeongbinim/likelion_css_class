# animation



요소에 애니메이션을 설정/제어

```
animation : 애니메이션이름|지속시간 [타이밍함수 대기시간 반복횟수 반복방향 전후상태 재생/정지];
```

```css
.box{
	width:300px;
  height:100px;
	animation : hello 2s linear both;
}

@keyframes hello{
  0%{width:300px;}	/*첫번째 프레임 0%대신 from 써도 됨*/
  100% {width: 50px;}	/*마지막 프레임 100%대신 to 써도 됨*/
}
```



### @keyframes

2개 이상의 중간 상태(프레임)을 지정한다.



------

### 속성

- animation-name : 함수 이름

- animation-duration : 지속시간

- animation-timing-function : 타이밍 함수 지정
  
  - ease : 빠르게 - 느리게(ease-out보다 정도가 큼)
  
  - ease-out : 빠르게 - 느리게
  
  - ease-in : 느리게 - 빠르게
  
  - ease-in-out : 느리게 - 빠르게 - 느리게
  
  - linear : 일정하게
  
  - cubic-bezier(n,n,n,n)//나만의 값을 정의
  
  - steps(n)//몇번의 애니메이션으로 보여줄지
  
    
  
- animation-delay : 애니메이션 대기 시간 설정(음수 허용 ex. 지속시간 3초일때 -1초면 2초지속)

- animation-iteration-count(default:1) : 애니메이션 반복 횟수 설정
  - 숫자
  - infinite 무한반복

- animation-direction(default:normal) : 반복 방향 설정
  - normal(정방향)
  - reverse(역방향)
  - alternate(정, 역 왕복)
  - alternate-reverse(역, 정 왕복)
  
- animation-fill-mode(default:none)
  - none : 기존 위치 시작 -> 애니메이션 시작 위치로 이동 -> 동작 -> 기존 위치에서 끝
  - forwards : 기존 위치 시작 -> 애니메이션 시작 위치로 이동 -> 동작 -> 애니메이션 끝 위치에서 끝
  - backwards : 애니메이션 시작 위치에서 시작 -> 동작 -> 기존 위치에서 끝
  - both : 애니메이션 시작 위치에서 시작 -> 동작 -> 애니메이션 끝 위치에서 끝

- animation-play-state(default: running)
  - running : 애니메이션 동작
  - paused : 애니메이션 동작을 정지

