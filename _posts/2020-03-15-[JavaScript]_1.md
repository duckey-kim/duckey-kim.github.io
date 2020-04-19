# JavaScript  
자바스크립트는 HTML과 CSS가 결합되고 웹페이지 상에서 올려진 후, 브라우저의 자바스크립트 엔진에 의해 실행됩니다. 이는 페이지의 구조와 스타일등을 정해놓고, 자바스크립트가 실행된다는 것과 같은 의미입니다.  
  
동적으로 사용자 인터페이스를 업데이트하는 자바스크립트의 사용은 Document Object Model API를 통해 HTML과 CSS를 수정하는 것으로 좋은 현상입니다. 만약 자바 스크립트가 HTML과 CSS 전에 실행되었다면 문제가 분명 발생할 것입니다.  
## Parse  
일련의 문자열을 의미있는 token으로 분해하고 프로그램을 compile하는 과정에서 프로그래밍 언어가 제시하는 syntax를 잘 지켜서 작성하는지 확인하고,구조를 알아내는 것이다.  


## 웹페이지가 만들어지는 순서  
`Web browser`가 원본 html문서를 읽어들인 후 , 스타일을 입히고 대화형 페이지로 만들어 viewport 또는 media에 표시하기 까지의 과정을 `Critical Rendering Path`라고 한다.  
 1. `Web Browser`는 읽어들인 문서를 `Parsing`하고 어떤내용을 렌더링 할지 결정한다.
 2. `Web Browser`는 정한 부분을 렌더링 한다.  


   


## DOM  
***documnet object Model***  
웹 페이지에 대한 인터페이스이다. 
## 실행순서  
브라우저에서 자바스크립트를 만났을 때 **일반적으로는** 위에서 아래 순서대로 실행됩니다. 이는 순서에 주의해서 코드를 작성해야한다는 의미입니다.  

## Compile과 Interprete의 차이  
JavaScript는 해석형 언어이다. 코드가 위에서 아래로 순차적으로 실행되고 그 즉시 결과를 반환한다. C/C++은 컴퓨터에 이해 aseembly language로 compile 되어 동작한다.  

## JavaScript를 작성하는 방법  

**내부의 JavaScript**  
```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>Apply JavaScript example</title>
    <script>
      document.addEventListener("DOMContentLoaded", function() {
        function createParagraph() {
          let para = document.createElement('p');
          para.textContent = 'You clicked the button!';
          document.body.appendChild(para);
        }

        const buttons = document.querySelectorAll('button');

        for(let i = 0; i < buttons.length ; i++) {
          buttons[i].addEventListener('click', createParagraph);
        }
      });
    </script>
  </head>
  <body>
    <button>Click me</button>
  </body>
</html>
```  

**외부의 JavaScript**  
`***.js`파일은 `index.html`이 위치한 폴더에 만든다. `.js`확장자는 이 파일은 JavaScript로 이루어져 있음을 이야기한다.  
`</body>`위에 아래의 코드를 추가한다.  
```html
<script src="***.js"></script>
```  
그리고 `***.js`의 파일에 다음소스를 추가한다.  
```javascript
function createParagraph() {
  let para = document.createElement('p');
  para.textContent = 'You clicked the button!';
  document.body.appendChild(para);
}

const buttons = document.querySelectorAll('button');

for(let i = 0; i < buttons.length ; i++) {
  buttons[i].addEventListener('click', createParagraph);
}
```  

**Inline JavaScript처리기**  
```html
<button onclick="createParagraph()">Click Me!</button>
<script>
  function createParagraph(){
    let para=document.createElement('p');
    para.textContent="You Clicked the Button!";
    document.body.appendChild(para);
  }
</script>
```  
이렇게 하면 `<button>`태그에 `onclick`속성에 대한 값으로 함수를 넣어 버튼이 클릭이 될때마다 `createParagraph()`함수가 실행된다.  
하지만 이방법은 이런 형태의 이벤트를 듣게 하려면 모든 태그에 `onclick="**()";` onclick에 대한 속성을 다 정의해 주어야 한다.  

## Script의 로딩방법  
작성된 HTML요소는 순서대로 페이지에 로드된다.만약에 JavaScript로 HTML의 요소에 어떤 행동을 주려할때 HTML의 요소보다 먼저 작성이 된다면 조작할 요소가 존재하지 않기때문에 제대로 동작을 하지 않을 것이다. 그렇기 때문에 script문을 `</body>`에 위치하게 한다.  

**내부 자바스크립트 예제**  

내부에 위치한 JavaScript예제를 보면 `<script>`태그가 `head`태그에 위치한 것을 볼 수 있다.

```javascript
documnet.addEventListener("DOMContentLoaded",function(){
..
});
```
`EventListener`는 `DOMContentLoaded`가 일어나게 되면 function()을 실행하게 된다. `DOMContentLoaded`는 브라우저가 완전히 로드되고 해석될때 발생이 된다. 즉 html의 모든 요소를 다 로드하고 function()을 실행한다고 할 수 있다. `</body>`태그위에 작성한 거와 같은 효과를 볼 수 있다.  

**내용정리**  

지금까지 배운 것을 정리해보면 HTML을 로드하던중에 script문을 만나게 되면 HTML을 로드하는 것을 멈추고 Script문을 로딩하고 파싱하게 된다. 만약에 Script문이 적용되어야 하는 HTML의 요소보다 위에 위치하게 되면 원하는 동작은 실행되지 않을 것이다. 그렇기때문에 Script문을 HTML의 요소들을 다 로드한 뒤인 `</body>`위에 위치하거나 `DOMContentLoaded`을 통하여 HTML 요소가 모두 로드된 후에 JavaScript문이 로드 파싱하게 만들었다.  
단! 이렇게 되면 HTML의 문서가 로드되기 전까지 JavaScript 코드는 로딩과 파싱이 진행되지 않는다. 결국 이 문제는 많은 JavaScript 코드를 다루는 웹페이지에서의 속도저하를 일으킬 수 밖에 없다.  

## async 와 defer  
둘다 비동기화로 JavaScript를 로딩하지만 `async`는  순서를 상관하지 않는다. `defer`는 순서를 중요시 한다. 만약 로딩해야대는 각각의 JavaScript가 연관관계가 있다면 `async`보다는 `defer`를 활용해야한다.  

```javascript
<script async src="js/vendor/jquery.js"></script>  3개의 .js중 어떤 것이 로드될지 모른다.

<script async src="js/script2.js"></script>

<script async src="js/script3.js"></script>
---------------------------------------------
<script defer src="js/vendor/jquery.js"></script>  jquery->script2->script3순으로 로딩된다.

<script defer src="js/script2.js"></script>

<script defer src="js/script3.js"></script>
```




