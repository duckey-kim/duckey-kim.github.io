# css속성 띄움,위치  
**목차**  
 - [float](#float)
 - [float의display수정](#display-수정)
 - [postion](#position)




## float  
요소를 좌우 방향으로 수평정렬한다. clear를 활용하여  
```clear: both;```정렬을 해제해줘야한다.  
**속성값**  
none : 기본 값  
left : 왼쪽으로 띄움  
right : 오른쪽으로 띄움  

**사용법**  
```css
.box {
    float: left;
}
```  
예제  
```html
<article class="studyarticle">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam ligula sapien, rutrum sed vestibulum eget, rhoncus
    ac erat. Aliquam erat volutpat. Sed convallis scelerisque enim at fermentum. Aliquam consectetur, est ac auctor
    iaculis, odio mi bibendum leo, <div class="picture"></div>in congue neque velit vel enim. Nullam vitae justo at
    mauris sodales feugiat.
    Praesent pellentesque ipsum eget tellus imperdiet ultrices.
    <div class="nopicture">
      Sed ultricies nisi nec diam sodales fringilla. Quisque
      adipiscing cursus porta. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam bibendum scelerisque
      elit,
      eu pharetra dui pulvinar eget. Nam mollis mauris id tellus ultricies at porttitor neque vulputate. Class aptent
      taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.
    </div>
</article>
```  

```css
.studyarticle>.picture{ 

    width: 70px;
    height: 150px;
    background: red;
    float :left;     ->왼쪽 정렬하겠다.
 
}

.picture>.nopicture{

   clear: left;    -> 왼쪽 정렬을 풀겠다.
}
```

<style>
.studyarticle>.picture{ 
   width: 70px;
   height: 150px;
   background: red;
   float :left;
   margin:10px;
}
.picture>.nopicture{
   clear: left;
}
</style>
<article class="studyarticle">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam ligula sapien, rutrum sed vestibulum eget, rhoncus
    ac erat. Aliquam erat volutpat. Sed convallis scelerisque enim at fermentum. Aliquam consectetur, est ac auctor
    iaculis, odio mi bibendum leo, <div class="picture"></div>in congue neque velit vel enim. Nullam vitae justo at
    mauris sodales feugiat.
    Praesent pellentesque ipsum eget tellus imperdiet ultrices.
    <div class="nopicture">
      Sed ultricies nisi nec diam sodales fringilla. Quisque
      adipiscing cursus porta. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam bibendum scelerisque
      elit,
      eu pharetra dui pulvinar eget. Nam mollis mauris id tellus ultricies at porttitor neque vulputate. Class aptent
      taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.
    </div>
</article>

### 수평정렬  
float의 속성에 들어가는 값을 left,right,none을 넣어보자.  
left는 왼쪽부터 정렬 , right는 오른쪽부터 정렬  
none은 수평이 아닌 수직정렬을 할 것이다. block요소처럼  
```html
<div class="boxs12">1</div>
<div class="boxs12">2</div>
<div class="boxs12">3</div>
<div class="box4">4</div>
```  
```css
.boxs12 {
   width: 100px;
   height: 100px;
   background:tomato;
   margin: 10px;
   float: none;  float에 left , right, none 을 입력해 보자.
}
.box4 {
    clear : both;
    display:block; -> 다음칸에 수직정렬시키기 위해서
}
```  
<style>
.boxs12 {
   width: 100px;
   height: 100px;
   background:tomato;
   margin: 10px;
   float: right; 
}
.box4 {
    clear : both;
    display:block; -> 다음칸에 수직정렬시키기 위해서
}
</style>
<div class="boxs12">1</div>
<div class="boxs12">2</div>
<div class="boxs12">3</div>
<div class="box4">위에는 float에 right를 넣은 오른쪽 정렬이다.</div>

### float 해제  
float이 적용된 요소 주위 다른요소까지 float이 적용될 수 있기때문에  
float 속성을 해제해야한다.  
 1. 다음 형제요소에 ```clear:both;``` 입력하여 해제한다.
 2. 다음 형제가 없을 때에는 부모요소에  overflow 속성을 추가한다.
 3. float 속성이 추가된 요소의 부모요소에 ```clearfix```클래스를 추가한다.
  
3가지 방법 모두 마지막의 요소에 ```clear:both;```값을 넣은 것과 같다.  

### display 수정  
float 속성이 추가된 요소는 display 속성의 값이 대부분 block으로 바뀐다.  
단 display:flex ,inline-flex는 변화가 없다.  

### clear  
float 속성이 적용되지 않도록 해제한다.  
```clear: xxx;```형태를 띈다.  
**속성값**  
none : 해제안한다.  
left : 왼쪽 float 해제  
right: 오른쪽 float 해제  
both: 왼쪽,오른쪽 float 해제  

## position  
요소의 위치 지정 방법의 기준을 설정한다.  
**속성값**  
static  : 유형 없음 배치 불가능 *기본값*  
relative : 요소 자신을 기준으로 배치한다.  
absolute : 위치상 부모 요소를 기준으로 배치  
fixed : 브라우저를 기준으로 배치  
sticky : 스크롤 영역 기준으로 배치  

기준이 잡히면 top,bottom,right,left를 작성한다.  
### top  
요소의 poistion 기준에 맞는 위쪽에서의 거리  

단위 :px,em등  
% : 부모 요소의 세로너비의 비율을 지정  

### bottom  
요소의 poistion기준에 맞는 아래쪽에서의 거리  
단위 : px ,em등  
% : 부모 요소의 세로너비의 비율로 지정  

### left right  
요소의 position기준에 맞는 왼쪽,오른쪽에서의 거리  
단위 : px,em등  
% : 부모요소의 가로너비의 비율로 지정한다.


### relative  
맨처음 자기 자신의 위치를 기준점으로 잡는다.  
top,bottom의 속성을 이용하여 옮겨도 기준점이 자신이기때문에  
원래의 위치에는 다른 형제요소들이 올라오는 것이 아니다.  
뭔가를 배치하는 경우에는 조심해야한다. 
```html
<div class="grand-parent12">
  <div class="parent12">
    <div class="child12">1</div>
    <div class="child12 absolute12">2</div>
    <div class="child12">3</div>
  </div>
</div>
```  
```css
.grand-parent12 {
   width: 400px;
   height: 300px;
   padding: 30px 100px 100px 30px;
   border: 4px dashed black;
  
}
.parent12 {
   width: 400px;
   height: 300px;
   border:4px dashed red;
  
}

.child12 {
width: 120px;
height: 80px;
background:tomato;
border: 4px dashed blue;
border-radius:10px;
font-size:30px;
display:flex;
justify-content: center;
align-items: center;


}
.absolute12{
   position:relative;
   top:50px;
   right:10px;

}
```  

<style>
.grand-parent12 {
   width: 400px;
   height: 300px;
   padding: 30px 100px 100px 30px;
   border: 4px dashed black;
  
}
.parent12 {
   width: 400px;
   height: 300px;
   border:4px dashed red;
  
}

.child12 {
width: 120px;
height: 80px;
background:tomato;
border: 4px dashed blue;
border-radius:10px;
font-size:30px;
display:flex;
justify-content: center;
align-items: center;


}
.absolute12{
   position:relative;
   top:50px;
   right:10px;

}
</style>
<div class="grand-parent12">
  <div class="parent12">
    <div class="child12">1</div>
    <div class="child12 absolute12">2</div>
    <div class="child12">3</div>
  </div>
</div>  
  



### absolute  
위치상의 부모요소를 기준으로 잡는다. position값이 부여되어 있는  
부모 요소가 있어야한다.static을 제외한 다른 속성값이 부여되어야 한다.  
부모요소에 position 속성값이 부여된게 없으면 viewport까지 올라가게 된다.  
예제!!  

```html
<div class="grand-parent">
  <div class="parent">
    <div class="child">1</div>
    <div class="child absolute">2</div>
    <div class="child">3</div>
  </div>
</div>
```  
```css
.grand-parent {
   width: 400px;
   height: 300px;
   padding: 30px 100px 100px 30px;
   border: 4px dashed black;
   position: relative;    position 의 속성값으로 relative부여함.
                          position:absolute; 의 기준점이 된다.
                          다른 부모요소들의 position 에 속성값이 부여된게 없기때문에.

}
.parent {
   width: 400px;
   height: 300px;
   border:4px dashed red;
  
}

.child {
width: 120px;
height: 80px;
background:tomato;
border: 4px dashed blue;
border-radius:10px;
font-size:30px;
display:flex;
justify-content: center;
align-items: center;


}
.absolute{
   position:absolute;  position 값이 부여된 부모요소를 찾아서 기준점으로 잡겠다.
   top:50px;           .child 에서 css가 적용된 box 가 grand-parent를 기준점으로
                       잡고 위쪽에서 50px 오른쪽에서 10위치로 옮겨질 것이다.
   right:10px;         relative 와 다르게 3번 box는 1번 밑으로 옮겨진다.

}
```  

<style>
.grand-parent {
   width: 400px;
   height: 300px;
   padding: 30px 100px 100px 30px;
   border: 4px dashed black;
   position:relative;
  
}
.parent {
   width: 400px;
   height: 300px;
   border:4px dashed red;
  
}
.child {
width: 120px;
height: 80px;
background:tomato;
border: 4px dashed blue;
border-radius:10px;
font-size:10px;
display:flex;
justify-content: center;
align-items: center;
}
.absolute{
   position:absolute;
   bottom:0;
   right:10px;
}
</style>
<div class="grand-parent">
  <div class="parent">
    <div class="child">1</div>
    <div class="child absolute">2</div>
    <div class="child">3</div>
  </div>
</div>


### fixed  
viewport의 위치를 기준으로 한다.  
```position:fixed;``` 스크롤이 있어도 항상 그위치에 있는다.  

### sticky  
스크롤 영역 기준으로 배치한다.  
sticky를 적용한 영역에서 top,bottom,left,right에서 고정한다.  
```css
.box{
    position:sticky;
    top,bottom,left,right등을 입력해줘야한다.
    left:0;
}
```  

### relative fixed sticky 의 차이  
 
<p class="codepen" data-height="265" data-theme-id="default" data-default-tab="html,result" data-user="duckey-kim" data-slug-hash="gOboxpm" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="gOboxpm">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/gOboxpm">
  gOboxpm</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  
sticky는 red색깔의 dashed border를 넘어가기 전까지 그 스크롤 영역 안에서의 sticky가 top쪽에서 계속 유지되는 것을 볼수 있다.  
relative는 자신의 위치를 기준으로 잡고 위치를 정한 것이기때문에 relative는 스크롤을 내리면 보이지 않게 된다.
fixed는 sticky처럼 red border영역이 아닌 전체의 viewport에서 고정이 되기때문에 스크롤을 내리고 올려도 항상 같은 위치에 있다.  
```html
<div class="scroll">
  <<div class="boxlayout">
    <span class="relative">relative</span>         relative , sticky ,fixed 라는  글자요소를 둔 span 태그를 3개를 작성 
                                                   boxlayout 을 넘어가면 어떻게 활용되는 지 보려한다.
    <span class="sticky">sticky</span>
    <span class="fixed">fixed</span>             
  </div>
  <div class="boxlayout">
    <span class="relative">relative</span>
    <span class="sticky">sticky</span>
   
  </div><div class="boxlayout">
    <span class="relative">relative</span>
    <span class="sticky">sticky</span>
   
  </div>
  
  
</div>
```  

```css
.scroll {
  width: 500px;
  height: 500px;
  background:yellowwhite;         스크롤 영역을 만들기 위해 overflow : auto;적용
  border:4px solid black;
  overflow:auto;
  }
.boxlayout {
  height: 200px;
  border: 4px dashed tomato;      높이 200px이 되는 하나의 영역을 만들어 준다.
  margin:10px;
}
.relative{
  font-size:40px;
  background:gray;
  position:relative;             글자크기를 40px을 갖고 자기자신위치에 기준을 잡고
                                 그 위치에서 위에서0px움직인 곳에 자리를 갖는다.
  top:0;
  
}
.sticky{
  font-size:40px;
  position:sticky;
  top:0;
  background:skyblue;           boxlayout 의 스크롤 영역안에서 위에서 0px움직인 곳에 자리를 잡는다.
}
.fixed {
  font-size:40px;
  position:fixed;
  top:20px;                     viewport에서 위에서 20px 위치한 곳에 고정시킨다. 
  background:yellow;
}
```


