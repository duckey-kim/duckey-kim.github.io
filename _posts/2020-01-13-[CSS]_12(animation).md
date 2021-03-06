# CSS 속성 애니메이션 & 다단  

## animation  
요소에 애니메이션을 설정/제어 한다.  *단축속성*  

```css
animation: 애니메이션 이름 지속시간 타이밍함수 대기시간;
```

### @keyframes  
애니메이션 중간 상태 프레임을 지정한다.  
@keyframes의 기본형태  
```css
@keyframes 애니메이션이름 {
    0% {속성,값 }
    50% {속성, 값}
    100% {속성,값}
}
```

### animation-name  
@keyframes 규칙에서 만든 이름을 지정  

### animation-duration  
애니메이션의 지속 시간을 설정 한다. *기본값=0*  

### animation-timing-function  
타이밍 함수를 지정한다. *기본값=ease* 빠르게 가다 느리게  

### animation-delay  
애니메이션의 대기시간을 설정한다. *기본값=0s*  

### animation-iteration-count  
애니메이션의 반복 횟수를 설정한다.  
숫자 또는 infinite 입력한다. *기본값=1*  

### animation-direction  
애니메이션의 반복 방향을 설정한다.  
nomarl : 정방향만 반복 *기본값*  
reverse: 역박향만 반복  
alternate : 정방향에서 역방향으로 반복(왕복운동)  
alternate-reverse : 역방향에서 정방향으로 반복(왕복)  

### animation-fill-mode  
애니메이션의 전후 상태를 설정한다.  

|값|의미|기본값|
|:---|:---|:---|
|`none`|기존위치에서 시작-> 애니메이션 시작위치로 이동 ->동작 -> 기존 위치에서 끝|none|
|`forwards`|기존위치에서 시작-> 애니메이션 시작위치로 이동 -> 동작 -> 마지막위치에서 종료| |
|`backwards`|애니메이션 시작위치에서 시작 -> 동작 -> 기존 위치에서 끝| |
|`both`|애니메이션 시작위치에서 시작 -> 동작 -> 마지막 위치에서 종료 ||  


### animation-play-state  
애니메이션의 재생과 정지를 설정한다.  

`running` : 애니메이션을 동작 *기본값*  
`paused` : 애니메이션 동작을 정지한다 
  
예제) 애니메이션이 동작하는 가운데 마우스를 갖다대면 애니메이션이 동작이 멈추는 것을 확인해보자.  

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="WNbWajJ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="animation-play-state">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/WNbWajJ">
  animation-play-state</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

원이 커지면서 before선택자를 이용하여 텍스트의 변화를 이용하여 애니메이션의 동작여부를 보여주고 있다. 마우스를 갖다대면 동작하고 있던 애니메이션이 배경색이 바뀌면서 running문구가 paused로 변화는 것을 볼 수 있다.


## multi-columns  
일반 블록 레이아웃을 여러 텍스트 다단으로 쉽게 정리하며, 가독성 확보.  
### columns  
```css
.text{
  columns:100px 2;
}
```  

columns-count : 컬럼의 갯수  
columns-width: 컬럼의 너비  
### column-rule  
단 사이의 선의 설정을 정의 한다.(like border)  

column-rule-width  : 두께  
column-rule-style : 종류  
column-rule-color : 색상  
**color**을 설정해주지 않으면  속한 태그의 color을 따라간다.

### column-gap  
단과 단사이의 간격을 설정한다.  
기본값: 1em (font-size)  









