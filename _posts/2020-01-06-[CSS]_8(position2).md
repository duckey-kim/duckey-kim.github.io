# CSS 위치에 대한 정의  
**목차**  



## 요소 쌓임 순서  
요소가 쌓여있는 순서를 통해 어떤 요소가 사용자와 가깝게 있는지를 결정한다.  
```position```의 속성값이 작성되어 있지 않으면 HTML에서 마지막 코드일 수록 위에 쌓인다.  

 1. ```static```을 제외한 ```position```속성의 값이 있을 경우 가장 위에 쌓임
 2. ```position```이 모두 존재한다면 ```z-index``` 속성의 숫자의 값이 높을 수록 위에 쌓인다.
 3. ```position```이 모두 존재하고 ```z-index``속성 값 또한 같다면 HTML의 마지막 코드일 수록 위에 쌓인다. 

예제) 5개의 박스를 만들어서 어떻게 쌓이는지 보자(box1~5까지 position 입력 X) 
<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="WNbdqox" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="position difference">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/WNbdqox">
  position difference</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

예제 5개의 박스를 만들고 box4,5에 ```position```의 속성값을 넣고, ```z-index```의 값을 부여한다.  
<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="YzPeKJj" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="duckey">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/YzPeKJj">
  duckey</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

box4에는 ```z-index:3;```을 주었고 box5에는 ```z-index:2;```을 주었다.  
```z-index```값이 큰 box4가 제일 위에 있고 그다음 box5가 위에 있다. box3,5는 멀리 떨어져있지만 box5는 ```position```값이 입력되어 있기때문에 3보다는 5가 더 위에 있다.  





