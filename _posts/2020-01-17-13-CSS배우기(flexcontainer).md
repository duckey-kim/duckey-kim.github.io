# CSS 배우기 flex items  

전에 올린 포스팅에서는 CSS에서의 Flex container를 배웠고 그 안에서의 축 정렬들을 배웠다. 이번에는 container의 안에 들어가는 items들을 배우려 한다.  

## Flex items  
**속성**

### order  
item의 순서를 설정한다.  item에 숫자를 지정하고 숫자가 클수록 뒤에 온다.  
 > HTML의 구조와 상관없이 순서를 변경할 수 있기 때문에 유용하다.  

단! order의 수치가 같을 때는 html의 순서를 따른다.  

```css
order: 숫자;
```  


### flex-grow  
item의 증가 너비 비율을 설정한다. 숫자가 크면 더 많은 너비를 갖는다.  
```css
flex-grow: 숫자; 기본값=0
```  
container안의 items들은 width을 지정해주지 않으면 가변되는 width를 갖는다.  

### flex-shrink  

item이 감소하는 너비의 비율을 설정한다. 숫자가 클수록 더 많은 너비가 감소한다.  
단! item이 가변 너비가 아니거나(width지정X), 값이 0일 경우 효과가 없다.  
```css
flex-shrink:감소너비;
```  

