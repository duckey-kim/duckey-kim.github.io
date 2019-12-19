## img / 빈태그

**속성**  
src : 필수 이미지 주소  

alt : 필수 이미지의 대체텍스트  

width, height : 크기를 줄이는 용도에 사용시    
                한쪽만 적용 하여도 된다.단위 px을 쓰지않음  
                css를 통해서도 크기 조절 가능  


srcset,sizes 사용시  src,alt는 무시된다.  
srcset, sizes 사용이 불가하면 src,alt로 대체된다.  

```html
<img
  srcset="images/heropy_small.png 400w,   경로, 실제가로크기
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"     
          브라우저가
          사용자 환경에 맞는 출력될 이미지 후보
  sizes="(max-width: 500px) 444px,     미디어 조건,조건시 최대사이즈   
         (max-width: 800px) 777px,
         1222px"
         최적화된 조건을 명시한다.
  src="images/heropy.png"
  alt="HEROPY" />
```  
<img
  srcset="images/heropy_small.png 400w,
           images/heropy_medium.png 700w,
          images/heropy_large.png 1000w" 
        sizes="(max-width: 500px) 444px,
         (max-width: 800px) 777px,
         1222px"
         src="images/heropy.png"
    alt="HEROPY"/>

  


### srcset 속성
경로와 원본을 지정한다. 2장 이상시 사용한다.
이미지 크기는 px이 아닌 w,x단위, 그리고 작은 크기부터 작성한다.  

#### w unit
가로너비 400x300 크기이면 가로너비는 400w이다.  
고정된 이미지 크기를 유지하려면 width="400"  
속성을 이용하면 된다.  

#### X unit  
이미지의 비율 의도를 의미한다.  

```html
<img
  srcset="images/heropy_small.png 1x,  small png기준
          images/heropy_medium.png 1.75x,
          images/heropy_large.png 2.5x"
  src="images/heropy.png"
  alt="HEROPY" />

  ```  
x단위 보다는 w단위를 쓰는 것이 더 좋다.  

#### sizes  
미디어 조건과 해당하는 이미지의 **최적화** 출력 크기를 지정한다.  
```html
<img
  srcset="images/heropy_small.png 400w,
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"
  sizes="(min-width: 1000px) 700px" 브라우저의 가로너비가 1000이상이면
                                    700px 출력을 사용한다.(medium)
  src="images/heropy.png"
  alt="HEROPY" />
```  

**width와 sizes의 차이점**
width는 가로길이를 유지하고 최적화된 파일을 계속 고른다. **우선적용**  
sizes는 srcset에서 최적화된 파일을 고르고 가로길이를 유지한다.