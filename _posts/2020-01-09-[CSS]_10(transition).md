# CSS 전환  
**목차**  
- [transition](#transition)
- [transform](#transform)   


## transition  
css의 속성의 전환효과를 지정한다. 시작과 끝을 지정하여 애니메이션 효과를 준다.  
transition-property : 전환효과를 사용할 속성이름 *기본값 = all*  
trasition-duration : 전환효과의 지속시간 설정  *기본값 = 0s*  
transition-timimng-function : 타이밍 함수 지정  
transition-delay : 전환 효과의 대기시간 지정  

### timingfunction  
**속성값**  
ease : 빠르게 -> 느리게  
linear : 일정하게  
ease-in : 느리게 -> 빠르게  
easy-in-out : 느리게 -> 빠르게 -> 느리게  

예제) Codepen을 활용하여 timing-function의 속성값에따른 차이를 봐보자.  
<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="MWYBgYQ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MWYBgYQ">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/MWYBgYQ">
  MWYBgYQ</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

이 코드를 만들면서 의도는 박스를 묶고 있는 container근처를 마우스에 갖다대면 box들이 변화하는 차이를 보여주려하였다.  
일단 div태그를 가로로 정렬하기 위해 ```display:inline-block;```을 설정하였다.  
다른 display속성값을 바꾸면서 flex을 사용하면 box의 생성마저도 transition되는 것을 알 수 있었다.  
많은 시뮬레이션을 거치면서 나온 결과는 이렇다.
모든 박스는 ```transition-duration:3s```이다. 하지만 변화하는 과정은 ```transition-timing-function```의 속성값에 따라 다른 결과를 보여준다.  

## transform  
요소에 변환효과를 지정한다. 속성값이 아닌 함수를 사용한다.  
position과 비슷한 효과를 내지만 transition을 사용하기에는 적합하지 않다.
```css
.box{
  transform: rotate(20deg) translate(10px,0);
}
```  

### tranfrom 2D 변환 함수  
이동
- translate(x,y) : x,y축 이동
- translateX(x) :x축 이동
- translateY(y) :y축 이동   

크기  
- scale(x,y) : x,y축 확대 축소  
- scaleX(x) : x축 확대 축소
- scaleY(y) : y축 확대 축소   

회전  
- rotate(degree) : 각도만큼 회전   

비틀기  
- skew(x-deg,y-deg) : x축,y축의 각도많큼 기울임
- skewX(x-deg) : x축 기울임
- skewY(y-deg) : y축 기울임   

통합  
- matrix(n,n,n,n,n,n,)   

예제)transform 변환함수  

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="MWYByXP" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="MWYByXP">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/MWYByXP">
  MWYByXP</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

### transform 3D 변환함수  
z축을 이용한 3D 변환함수 이다. scss를 배운 후에 배워보자.  
```css
transform: translate3d(x,y,z);
transform: rotate3d(x,y,z);
transform: perspective(단위);
```


### transform 변환 속성  

| 속성|의미 |
|:---|:---|  
| `transform-origin` | 요소 변환의 기준점 |
| `transform-style` | 3D 변환 요소의 자식 요소도 3D변환 할지 설정 |
| `perspective` | 하위 요소를 관찰하는 원근 거리 설정 |
| `perspective-origin` | 원근 거리의 기준점 설정 |
| `backface-visibility` | 3D변환으로 회전된 요소의 뒷면을 가린다. |

#### transform-origin  

| 값|의미|기본값|
|:---|:---:|---:|  
|X축 | `left`,`right`,`center`,단위 | 50%|
|Y축 | `top`,`bottom`,`center`,단위 | 50%|
|Z축 | 단위 | 0|  


#### transform-stlye  

|값|의미|기본값|
|:---|:---|:---|
|`flat`|자식요소의 3D변환을 사용하지 않는다.|flat|
|`preserve-3d`| 자식요소도 3D변환 허용 |**자식만 허용한다.** |

### perspective  
하위 요소를 관찰하는 원근거리를 설정한다. *함수가 아닌 속성이다*  
px을 입력하여 활용한다.  
|속성/함수|적용대상|기준점 설정|
|:---|:---|:---|
|`perspective`*속성*|관찰 대상의 **부모**요소 | `perspective-origin`|
|`transform:perspective(**px);`*함수*|관찰대상의 요소 | `transform-origin`|  
  
함수와 속성의 차이  

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="zYxJNWx" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="perspective함수와 속성의 차이">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/zYxJNWx">
  perspective함수와 속성의 차이</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

속성은 하위요소의 변화들을 모두 관찰하기때문에 부모요소에 정의해주는 것이 좋다.  
함수는 자기자신의 요소가 변화를 관찰하기때문에 요소의 위치에 정의를 한다.  
그렇기때문에 당연히 두 결과의 값이 다를 수 밖에 없다. 속성은 모든 transform을 관찰하였고 함수는 rotateX의 transform만 관찰한 것을 볼 수 있다.




#### perspective-origin  
원근거리의 기준점을 선정한다.  

|값|의미|기본값|
|:---|:---|:---|
|`X축`|`left`,`right`,`center`,단위|50%|
|`Y축`|`top`,`bottom`,`center`,단위|50%|

### backface-visibility  
3D 변환으로 회전된 요소의 뒷면 숨김을 설정한다.  
visible 화면 보임 *기본값*  
hidden 화면 숨김  

예제) visible 과 hidden 의 차이  
***두 그림을 클릭해보세요***  


<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="WNbazGZ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="WNbazGZ">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/WNbazGZ">
  WNbazGZ</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

두 이미지 모두 ```rotateY(180deg)```을 transform 하였다.  
왼쪽은 ```backface-visibility: visible;```을 적지 않았지만 기본값이 적용되었다.  
오른쪽은 ```backface-visibility:hidden;```을 적용하였다.  
그래서 왼쪽 이미지를 클릭을 하면 고양이의 꼬리가 오른쪽 으로 간 것으로 화면이 반전 된 것을 알 수 있다.  
하지만 오른쪽 이미지를 클릭하면 90도쯤 돌아갔을 때 부터 화면이 보이지 않는다. 이것이 ```backface-visibility:hidden;```의 역할이다.  










