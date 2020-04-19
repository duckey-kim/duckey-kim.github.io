# CSS배우기 Grid item 함수/단위

## repeat  
`repeat()` 함수는 행/열 의 크기 정의를 반복할때 사용한다.  
(반복되는 횟수) / 행또는 열의 크기 정의를 인수로 사용한다.  

```css
.container{             repeat() 함수 사용 X
    grid-template-rows:100px 100px 100px 100px;
}

.container{             repeat() 함수 사용 O
    grid-template-rows: repeat(4,100px);  행의 크기를 100px 4번 
    grid-template-rows: repeat(2,100px 100px);  위와 같은 결과가 나온다.
    grid-template-rows: repeat(4,[row-start] 100px [row-end]); 선의 이름도 넣을 수 있다.
}
```  


## minmax()  
`minmax()`함수는 행/열의 최소/최대크기를 정의한다.  
첫 번째 인수는 최솟값  이고 두 번째 인수는 최댓값이다.  
`grid-template-rows/columns`,`grid-auto-rows/columns`에서 사용한다.  

```css
.container{
    grid-template-columns:minmax(100px, 1fr) minmax(200px, 1fr);
                        1열의 가로크기 정의        2열의 가로크기 정의
     1fr을 유지하다 100px보다는 작아질 수 없다.     1fr유지하다 200px보다는 작아질 수 없다.
}
```  

## fit-content  
`fit-content()` 함수는 행/열 의 크기를 그리드 아이템이 포함되는 내용 크기에 맞춘다.  
**인수**는 최대 크기를 사용한다. `minmax(auto,max-content)`와 유사하다.  

```css
.container{
    grid-template-columns:fit-content(300px) fit-content(300px);
                            1열의 크기를 content에 맞추지만 content가 300px를 넘어가면 크기를 300px에 고정한다.
}
``` 

# grid units  
grdi 에서 사용하는 주요 단위를 알아보자.  

## ft  
ft(fractional unit) 사용 가능한 공간 을 비율로 표시한 것이다. 부여한 특정 값들을 사용하고 남은 것을 비율로 나눠 갖는다고 생각하면 쉽다.  

```css
.container{
    grid-template-columns: 1fr 3fr 100px 25% ;  
    
    1fr 3fr 100px 25%로 행의 가로크기를 부여하였다. 3열,4열의 가로크기 100px 25%를 사용하고 남은 공간을 1:3 비율로 1열과 2열이 나눠 갖는다
}
```  

## min-content  
Grid item이 갖고 있는 content의 최소 크기를 의미한다.

## max-content  
Grid item이 갖고 있는 content의 최대 크기를 의미한다.


### min-content,max-content활용  

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="duckey-kim" data-slug-hash="wvaWrMo" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="min-content max-content">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/wvaWrMo">
  min-content max-content</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>  

`word-break:keep-all` 은 `min-content`가 한글을 하나의 글자를 content로 인식하는 것을 막아준다.  만약에 `word-break`을 입력하지 않으면 `min-content`는 한글자크기를 min-content값으로 인식하여 한줄에 한글자만 오게 한다.  


## auto-fill, auto-fit  
행과 열의 개수를 지정할때 행과 열의 크기에 맞게 자동으로 조정하게 한다.  
`repeat()`의 함수와 같이 사용하고 첫번째 인수인 반복 횟수 인수에 적용할 수 있다.  명확한 행과 열의 개수가 필요하지 않은 경우 사용하면 좋다. 

```css
.container{
    grid-template-columns:repeat(auto-fill,minmax(120px,1fr));
                        최소값 120px 그이상은 1:1비율로 자동으로 생성한다.  
}
```  

`auto-fill`과 `auto-fit`의 차이점은 행과열을 배치하고 Grid container에 공간이 남아있을때 차이가 생긴다.  
`auto-fill`은 남아있는 공간을 그냥 냅두고 그공간들과 같이 배치한다.  
`auto-fit`은 남아있는 공간을 축소시켜버리고 배치된 행또는 열을 늘린다. 다른 행 또는 열은 축소된것을 개발자 도구로 볼 수 있다.  

### auto-fill 과 auto-fit의 차이점  

<p class="codepen" data-height="265" data-theme-id="default" data-default-tab="css,result" data-user="duckey-kim" data-slug-hash="jOPrdRx" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="different with auto-fill and auto-fit">
  <span>See the Pen <a href="https://codepen.io/duckey-kim/pen/jOPrdRx">
  different with auto-fill and auto-fit</a> by duckey-kim (<a href="https://codepen.io/duckey-kim">@duckey-kim</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
  
firefox창에서 개발자도구에 들어가서 첫 번째와 두 번째의 grid-container의 행 또는 열의 배치를 보면 차이점을 알 수 있다. 