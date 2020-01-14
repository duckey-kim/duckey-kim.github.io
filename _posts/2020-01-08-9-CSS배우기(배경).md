# CSS 배우기 background  
**목차**  
- [background](#background)
- [color](#color)
- [image](#image)
- [repeat](#repeat)
- [position](#position)
- [attachment](#attachmment)
- [SIZE](#size)  




## background  
요소배경을 설정한다. 색상,이미지,위치,스크롤 여부등 단축속성이다.  
**사용법**  
```background : 색상 이미지경로 반복 위치 스크롤 특성;``` 다 사용할 필요는 없다.  
```css
.box1{
    background: red url('asdf.jpg') no-repeat left top scroll;
}
```  
### color  
배경의 색상을 설정한다.  
기본값 : transparent 즉 투명값이다.  
```background-color:red;```의 형태로 사용한다.  

### image  
요소의 배경에 하나 이상의 이미지를 삽입한다.  
기본값 : none 이미지가 없다.
```background-image:url('주소'),url('주소2'),;```의 형태를 사용한다.  
단축속성으로 작성시   
```background: url('주소') no-repeat,url('주소2') 100px,50px;```  
***단!*** 배경에 이미지 삽입시 , 요소의 크기가 설정되어야 한다. 먼저 입력한 배경이 위에 오게 된다.  

### repeat  
배경이미지의 반복을 설정한다.  
repeat :배경 이미지를 수직,수평으로 반복 *기본값*  
repeat-x : 배경 이미지로 수평으로 반복  
repaet-y : 배경 이미지를 수직으로 반복  
no-repeat : 반복하지 않는다.  

### position  
배경이미지의 위치를 설정한다.  
```background-position: ;```
**속성값**  
% : 0~100% 왼쪽 상단 모서리는 0% 0% 오른쪽 하단 모서리는 100% 100% 
방향: 방향을 입력하여 위치설정한다. top center bottom left right  
> 단위 입력시에는 처음이 **x축** 뒤에는 **Y축**으로 인식한다. 단위와 방향을 조합해서 쓸 경우 좌우 부터 먼저 입력해야한다.  

## attachment  
요소가 스크롤될 때 배경이미지가 스크롤에 어떻게 반응 할지 설정한다.  
scroll : 배경 이미지가 요소를 따라서 같이 스크롤 된다. *기본값*
fixed : 배경 이미지가 viewport에 고정되어 있다.  
local : 요소내 스크롤시 배경이미지가 같이 스크롤 된다.  
**예제**  
똑같은 배경이미지를 둔 div 박스를 scroll에 따라 어떤 반응을 보이는지 봐보자.

<p class="codepen" data-height="315" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="VwYxMNW" style="height: 315px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="VwYxMNW">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/VwYxMNW">
  VwYxMNW</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

왼쪽 박스는 ```background-attachment:scroll;```을 적지 않았지만 기본값이다.  
오른쪽 박스는 ```background-attachment:fixed;```을 적용하였다.  
왼쪽 박스는 container 박스가 움직일때 와 body클래스의 스크롤이 움직일때 모두 움직인다.  
하지만 오른쪽 박스는 container 박스가 움직여도 배경화면은 움직이지 않는다. 왜냐하면 
fixed가 적용이 되면 배경이미지는 *viewport에 고정이 된다.*  
container의 박스의 스크롤을 움직여도 viewport는  움직이지 않기때문에 *배경이미지는 움직이지 않는다.*  
그렇기때문에 viewport의 변화를 주는 전체스크롤이 움직여야 오른쪽 박스의 배경이미지가 움직이는 것을 볼 수 있다.

### size  
배경 이미지의 크기를 지정한다.  
```background-size: width height ;``` 의 형태를 쓴다.  
```width```만 쓰더라도 비율에 맞게 지정한다.  
**속성값**
auto : 배경 이미지 원래의 크기를 표시한다. *기본값*  
cover : 배경 이미지 크기의 비율을 유지하며 요소의 더 넓은 너비에 맞춰진다.**이미지가 잘릴 수 있다.**  
cotain : 배경 이미지 크기의 비율을 유지하며 요소의 더 짧은 너비에 맞춰진다.**이미지가 잘리지는 않지만 빈 공간이 생길 수 있다.**  

예제)```background-size:cover,contain;```의 차이  
<p class="codepen" data-height="450" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="QWwrebN" style="height: 450px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="QWwrebN">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/QWwrebN">
  QWwrebN</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

cover는 요소에 딱 맞춰서 배경이미지를 넣지만 이미지가 짤린다.  
contain은 요소의 작은 요소에 맞춰서 이미지의 짤림은 없지만 빈 공간이 생긴다. 그래서 빈 공간은 채우려하기 때문에 ```background-repeat:no-repeat;```을 설정해 주었다.  












