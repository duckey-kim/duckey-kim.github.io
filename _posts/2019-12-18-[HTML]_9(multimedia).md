# 멀티미디어 태그들  

## audio태그  
**속성**  

autoplay - 바로 재생  
controls - 제어 메뉴  
loop     - 재생이 끝나면 다시 재생  
preload  - 파일을 로드할지 지정  
src      - 오디오 파일 url  
muted    - 음소거  

[audiotag MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/audio)  
```html  
<audio src="https://interactive-examples.mdn.mozilla.net/
media/examples/t-rex-roar.mp3" controls muted></audio>
```  
<audio src="https://interactive-examples.mdn.mozilla.net/
media/examples/t-rex-roar.mp3" controls muted></audio>  


## video 태그  
동영상 콘텐츠를 삽입한다. mp4파일을 주로 사용  
**속성**  
autoplay    - 바로 재생  
controls    - 제어 메뉴  
crossorigin - 외부페이지에서 가져올때 동일안 출처 확인  
loop        - 다시 재생  
muted       - 음소거  
poster      - 동영상 썸네일 이미지 URL  
preload     - 페이지 로드시 동영상 로드할지의 지정  
src         - 콘텐츠 URL  
width       - 영상의 가로 너비  
height      - 영상의 세로 너비  

[video tag MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Video)  

```html
<video src="https://interactive-examples.mdn.mozilla.net
/media/examples/flower.webm"
autoplay controls loop muted  자동재생,menu,다시재생,음소거 상태
poster="./iamges/heropy.png"> 포스터 이미지의 주소
</video>
```

<video src="https://interactive-examples.mdn.mozilla.net
/media/examples/flower.webm"
autoplay controls loop muted  ></video>  

## figure , figcaption태그  
이미지와 이미지의 설명등을 묶어주는 영역을 설정한다.  

```html
<img src="./images/heropy.png" alt="헤로피 이미지">
    <p>헤로피 이미지 입니다.</p>
```  
figure와 figcaption을 활용하여 바꾼다.  

```html
   <figure>
        <img src="./images/heropy.png" alt="헤로피 이미지입니다.">
        <figcaption>해로피 이미지 입니다.</figcaption>
    </figure>
```
p태그를 figcaption으로 바꾸어서 브라우저가 img와  
img에대한 설명하는 구조라는 것을 알게 해준다.  

### iframe 태그
다른 html페이지를 현재 페이지에 삽입한다.  
보안적인 이슈가 있다.  
  

**속성**  
name        - 프레임의 이름  
src         - 동영상의 url  
frameborder - 외각선 0,1
width       - 가로너비  
height      - 세로너비  
sandbox     - 보안강화용 allow-script


```html
    <div>
        <img src="./images/heropy.png" alt="사진">
    </div>
    <div>
        <iframe src="https://fastcampus.co.kr" frameborder="0" width="70%"
        height="400px" style="border: 2px solid red"></iframe>
    </div>
```  

<iframe src="https://fastcampus.co.kr" frameborder="0" width="70%"
        height="400px" style="border: 2px solid red"></iframe>

### canvas 태그  
Canvas API , WebGL API를 사용하여 그래픽이나  
애니메이션을 랜더링 하는 영역를 지정한다.  

**속성**
width   - 캔버스의 가로 너비  
height  - 캔버스의 세로 너비  

[Canvas tag MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Canvas/Tutorial/Basic_usage)  

### script 태그  
외부의 스크립트를 문서에 포함하거나 참조한다.  
javascript는 script로 css 는 link로 가져왔다.  
**src**속성은 **_필수이다_**!!. 

**속성**  
async       - 스크립트의 비동기적 실행 여부  
              동기적 실행 순차적, 비동기적은 비순차적이다.  
**defer**       - html문서를 다 분석한 후에 script를 실행해라.  
src         - 참조할 외부 스크립트 URL  
            src 작성시 script안의 코드들은 무시된다.  




```html
    
    <div id="my-name">HEROPY!</div>
    <script src="./js/main.js">
    console.log('안녕하세요~');
    </script>
```  
script의 src를 작성하여서 script안의
console.log는 실행이 되지 않는다.  

```html
    
    <div id="my-name">HEROPY!</div>
    <script>
    console.log('안녕하세요~');
    </script>
```  
script의 src작성을 하지않으면 console의  
log를 작성된 것을 볼 수 있다.
![Nosrc_script](https://raw.githubusercontent.com/duckey-kim/duckey-kim.github.io/master/_posts/nosrc_script.png"src 작성 안할시의 consolelog")  


### noscript 태그  
스크립트를 지원하지 않는 경우에 삽입함  


## table 만들기  
 ```<table>```  테이블 표 만들때 블록요소와 비슷하다.  
 ```<tr>```  행을 만들때  
 ```<td>,<th>```  열을 만들때 사용한다.  

### th 태그  
머리글 칸 을 지정  

**속성**  
abbr    - 열에 대한 설명  
headers - 관련된 하나의 머리글칸 id  
colspan - 확장하려는 병합하려는 열의 수**수평**  
rowspan - 확장하려는 병합하려는 행의 수**수직**  
scope  - 누구의 머리글 칸인지 명시 

### td 태그  
**속성**  
headers - th의 id값을 연결  
colspan - 열 병합  
rowspan - 행 병합  

### caption 태그  
표의 제목을 설정.
- 열리는 table 태그 바로 다음 작성한다.
- table 태그당 하나의 caption을 사용한다.  

### colgroup, col 태그  
표의 열등을 공통적으로 정의한다.
span 연속되는 열 수

#### col 태그  
빈태그 형식  

#### thead,tbody,tfoot 태그  
표의 머리글,본문,바닥글을 지정한다.  
테이블의 레이아웃에 영향을 주지는 않는다.  
th들을 thead로 th제외 다른 부분을 tbody로 묶는다.  



```html
  <table style="border-collapse: collapse;">

        <tr>
            <th style="border: 1px solid red;">타입</th>
            <th style="border: 1px solid red;">값</th>
            th는 테이블의 머리글 용으로 사용된다.
        
        </tr>
        <tr>
            <td  style="border: 1px solid red;">알파벳</td>
            <td  style="border: 1px solid red;">a</td>
        </tr>
        <tr>
            <td  style="border: 1px solid red;">숫자</td>
            <td style="border: 1px solid red;">7</td>
        </tr>
    </table>
```
  <table style="border-collapse: collapse;">

        <tr>
            <th style="border: 1px solid red;">타입</th>
            <th style="border: 1px solid red;">값</th>
        </tr>
        <tr>
            <td  style="border: 1px solid red;">알파벳</td>
            <td  style="border: 1px solid red;">a</td>
        </tr>
        <tr>
            <td  style="border: 1px solid red;">숫자</td>
            <td style="border: 1px solid red;">7</td>
        </tr>
    </table>  
물론 이 것은 css로 작성하여 link 태그를  
활용하는 것이 좋으나 포스트 위해서  
이렇게 작성하였다.

```html
<table>
        <tr>
            <th colspan="2" id="th-data">데이터</th>
            colspan 행을 합치는데 2개를 합치고 아이디는 th-data이다.

        </tr>

        <tr>
            <th abbr="Type" scope="col" headers="th-data">타입</th>
            th가 type라는 설명 자신의 행이 머리글 칸이면 th-data의 더 상위의 머리글
            <th abbr="Value" scope="col" headers="th-data">값</th>
        </tr>
        <tr>
            <td>알파벳</td>
            <td>a</td>
        </tr>
        <tr>
            <td>숫자</td>
            <td>7</td>
        </tr>
    </table> 
```  
```html
<table>
        <caption>데이터 타입과 값</caption>
        <colgroup>
            <col>
            <col style="background-color: tomato;" span="2">
            colgroup으로 col을 묶고 2번째 열부터 span=2
            총 2개의 열도 style을 적용한다.
        </colgroup>

        <tr>
            <th></th>
            <th>타입</th>
            <th>값</th>
        </tr>
        <tr>
            <th>1</th>
            <td>알파벳</td>
            <td>a</td>
        </tr>
        <tr>
            <th>2</th>
            <td>숫자</td>
            <td>7</td>
        </tr>

    </table>
```  

<table>
        <caption>데이터 타입과 값</caption>
        <colgroup>
            <col>
            <col style="background-color: tomato;" span="2">

        </colgroup>

        <tr>
            <th></th>
            <th>타입</th>
            <th>값</th>
        </tr>
        <tr>
            <th>1</th>
            <td>알파벳</td>
            <td>a</td>
        </tr>
        <tr>
            <th>2</th>
            <td>숫자</td>
            <td>7</td>
        </tr>

    </table>



