# CSS FLEX  

**목차**  


요소들을 수평정렬할때 지금까지 활용했던 방법은  
```html
<div class="container clearfix">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```  
```css
.clearfix::after{   container 가 item 들을 묶는 형태를 만들기 위해 활용
  content:"";
  display:block;
  clear:both;
}
.container{
border:2px solid red;

}

.container .item {     float 은 item들을 수평으로 보여주게는 해준다. 
  float:left;
  width: 100px;
  height: 100px;
  border:2px solid;
  border-radius:10px;
}
```  

clearfix와 float은 없앤우 .container에 `display:flex;`만 부여하면 해결된다.  
기본구조는 container 가 부모요소이고 item이 자식요소 라는 느낌으로 배워보자.  

## Flex container  
  
|속성|의미|  
|:---|:---|
|`display`|Flex container를 정의한다.|
|`flex-flow`| 기준 축과 묶음을 설정한다.|





### display    

|값|의미|
|:---|:---|
|`flex`|container 자체는 block요소이다.|
|`inline-flex`|container 자체가 inline요소가 된다.|  

container 안의 item들이 inline 요소처럼 수평정렬되는 것은 같지만  
container 자체의 속성이 block,inline요소로 인식이 된다.


### flex-flow  

|값|의미|기본값|
|:---|:---|:---|
|`flex-direction`|item의 주축 정렬을 설정한다.|row|  
|`flex-wrap`|item들의 묶음할 줄의 수 설정|nowrap|  

#### flex-direction  

**수평정렬**  
row : item들을 수평으로 정렬한다(왼쪽정렬)  
row-reverse: row의 반대  
**수직정렬**  
column: item들을 수직으로 정렬한다.(위에서 아래로)  
column-reverse : 아래서 위로 정렬  

***수평정렬과 수직정렬은 주축,교차축이 된다.(상대적개념)***  
각 정렬의 시작점과 끝점은 reverse에 따라 다르다.  

### flex-wrap  
items의 여러줄 묶음을 설정한다.  

|값|의미|기본값|
|:---|:---|:---|
|`nowrap`|item들을 무조건**한 줄**에 묶음|nowrap|  
|`wrap`|item들을 여러 줄로 묶음 `container`의 크기에 맞춤| |
|`wrap-reverse`|역방향으로 여러 줄로 묶음| |  

container의 안에 있는 item들은 width,height의 값이 가변할 수 있다.  

### justify-content  
주 축의 정렬 방법을 설정한다.  

|값|의미|기본값|
|:---|:---|:---|
|`flex-start`|item의 시작점으로 정렬|`flex-start`|  
|`flex-end`|item를 끝점으로 정렬| |
|`center`|item들을 가운데 정렬한다.| |
|`space-between`|시작점에서 시작 마지막을 끝점으로 정렬하고 사이는 고르게 정렬| |  
|`space-around`|item들이 균등한 공간을 가지고 정렬| |  

### align-content  
교차 축의 정렬 방법을 설정한다. 단! `flex-wrap:wrap;` 의 속성을 통해 items가 2줄이상이고 여백이 있어야한다.  
items가 한 줄이면 `align-items`을 사용한다.  

|값|의미|기본값|
|:---|:---|:---|
|`stretch`|item의 교차축의 크기를 늘리어서 사용한다.|`stretch`|
|`flex-start`|item의 교차축의 시작점으로 정렬| |  
|`flex-end`|item를 교차축의 끝점으로 정렬| |
|`center`|item들을 교차축의 가운데 정렬한다.| |
|`space-between`|시작점에서 시작 마지막을 끝점으로 정렬하고 사이는 고르게 정렬| |  
|`space-around`|item들이 균등한 공간을 가지고 정렬| |  


### align-items  
교차 축에서 items의 정렬 방법을 설정한다. items이 두 줄 이상이라면 우선적으로 `align-content`가 적용되어야한다. 한 줄이때만 사용하는 것이 좋다.


|값|의미|기본값|
|:---|:---|:---|
|`stretch`|item의 교차축의 크기를 늘리어서 사용한다.|`stretch`|
|`flex-start`|item의 교차축의 시작점으로 정렬| |  
|`flex-end`|item를 교차축의 끝점으로 정렬| |
|`center`|item들을 교차축의 가운데 정렬한다.| |
|`baseline`|items를 문자선에 정렬한다.||






