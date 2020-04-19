# bootstrap  
배우고 인터넷 서칭을 하면서 필요한 부분을 활용하여 홈페이지를 만들어 보았지만 완성된 모습을 보면 다음홈페이지에 비해 형편이 없다.  
bootstrap을 활용하면 내가 원하는 내용의 형태를 끌어다 땡겨 올 수 있기때문에 이번에는 bootstrap을 한번 활용하여 나만의 사이트?를 다시 만들어 보려고 한다. 이 글에는 내가 bootstrap을 활용하면서 느끼거나 특징적인 부분을 적어보려고 한다.  

## 주의점!!  
**bootstrap의 버전 check!**  

bootstrap의 버전을 잘 확인하자.한글어 버전의[bootstrap-korea](http://bootstrapk.com/getting-started/)은 버전이 3.3.2이고 영어 버전의[bootstrap-english](https://getbootstrap.com/)의 버전은 4.4.1이다 . 처음에는 3.3.2로 작성하였다가 다른 bootstrap library사용하면서 영어버전의 사이트를 활용하다보니 3.3.2버전의 library가 안먹히는 경우가 생겼다.  

## 내가 작성한 HTML에 bootstrap 적용시키기  
bootstrap은 다양한 클래스를 통해서 css를 적용시킬 수 있는 라이브러리 라고 생각할 수 있다. 그 라이브러리를 불러오기위해서는 bootstrapCDN을 활용하면 된다.  
 1. `html`의 `head`부분에 link태그를 통해 `bootstrap`의 `css`파일을 불러온다.  

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
```  

 2. `bootstrap`의 다양한 component들은 `javaScript`의 function을 활용한다. 그렇기 때문에 [jQuery](https://jquery.com/) 와 [popper](https://popper.js.org/)을 사용해야한다. `body`태그 끝부분에 처음에는 `jQuery`,`popper.js`,마지막으로 bootstrap의 plugin을 작성해 준다.  

```html
<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>
```  


## mobile 우선적  
media크기 또는 viewport 크기의 변화에 따른 적절한 렌더링과 확대/축소를 위해 `viewport`메타 태그가 추가되어 있다.  
`container`의 형태도 2가지 이다. 반응형 콘테이너는 `.container` 최대폭 컨테이너는 `.container-fluid`를 활용한다.  
```html
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
```

## grid system 12 columns  
부트스트랩은 기기나 뷰포트 크기가 증가함에 따라 **12열이** 적절하게 확대되는 반응형, 모바일 우선 유동 그리드 시스템입니다. 그것은 쉬운 레이아웃을 위해 미리 정해진 클래스들 뿐만 아니라 강력한 더 시멘틱한 레이아웃을 생성하기 위한 믹스인 을 포함하고 있습니다.  

***예제***  
만약에 같은크기의 2개의 열을 쓰고 싶다면 `.col-xs-6` 2개를 사용하면 된다. 
쉽게생각해서 12 나누기 원하는 갯수의 열을 나누어주고 사용하자  

## grid option  

||모바일 768px이하|태블릭 768px이상|데스크탑 992px이상|큰기기 1200px이상|
|**grid**|항상|768px이상이면 |992px이상이면|1200px이상이면|
|**container width**|auto|750px|970px|1170px|
|**column width**|auto|~62px|~81px|~97px|
|**class name**|`.col-xs-숫자`|`.col-sm-숫자`|`.col-md-숫자`|`.col-lg-숫자`|

## 사용하려는 bootstrap  
 -[container](#container)  
 -[button](#button)  
 -[nav-pills](#pills)  
 -[row-columns](#row-columns)  
 -[table](#table)  


## container  
우리가 사용하던 `container`들은 items들을 wrap 하는데 많이 사용한다. bootstrap에서도 그런 용도로 사용되며 **반응형**으로 사용되는 `container`의 종류에는  2개가 있다.  
1. `container` : 반응형으로써 media의 화면 크기의 따라서 크기가 정해져있다.  
2. `container-fluid` : 반응형으로써 media의 화면 크기에 가득 채운다.  


## pills 
`html5`에서 `nav`태그는 네비게이션 역할을 담당한다. `div`태그로 생성은 할 수 있지만 다른사람들에게도 통용되는 `nav`태그를 사용하였다.  
`nav`의 종류에서도 bootstrap에서 `nav-pills`형태의 라이브러리를 활용한다.

```html
<div class="container-fluid">                             가득찬 container
  <div class="row">                                       한줄만 사용
    <div class="col-sm-10">
       <nav class="nav nav-pills ">                        nav중에서도 pills nav 사용
         <a class="nav-link" href="nav1.html">Nav 1</a>
         <a class="nav-link" href="nav2.html">Nav 2</a>
         <a class="nav-link" href="nav3.html">Nav 3</a>
        <a class="nav-link" href="nav4.html">Nav 4</a>        
      </nav>
    </div>
  </div>
</div>
```  


## row-columns  
 - `row` 클래스는 container나 container-fluid 안에 있어야 정상적인 배열이나 패팅을 지원해준다.  
 - 12개의 `column`을 over 하게되면 새로운 줄로 column이 배치된다.  
 - 내용은 작성하는 곳은 `row`가 아닌 `column`이 되어야 한다!  

## button  
[button](https://getbootstrap.com/docs/4.4/components/buttons/)  

`<button>`태그만이 아닌 `<a>`,`<input>` 태그에서도 `button`태그의 요소를 활용할 수 있다. `.btn`을 사용하여 `<a>`태그에 `.btn`클래스를 부여하면 사이트를 이어주는 역활을 할 수 있는 **Button**으로 구현이 된다.  


### 계획과 실행  

홈페이지에 들어왔을 때 4개의 메뉴에 최신 게시물들을 보여주는 board를 만들고 싶다.  
그래서 하나의 row에 2개의 column이 들어가는 row로 형성하려고 한다. 그래서 2개의 row를 만들려고 했지만 어차피 viewport 또는 media의 크기에 따라 2개의 행일 될 수 도 있고 1개의 행이 될 수 도 있다. 그렇기 때문에 1개의 row로 묶어도 되고 2개의 row로 묶어도 된다. 
어차피 한개의 row는 12개의 columns으로 이루어져 있고 그것을 넘어가면 auto-flow가 되기 때문이다.  


```html
<div class="container-fluid"> 4개의 게시판을 보여주는 container
  <div class="row">           1개의 row
    <div class="col-sm-6">    sm크기의 행 6개를 활용한다. -> 6개의 행을 활용하는 column 2개를 쓴다. 1row를 2개의 부분으로 나눈다.
      <table class="table">   행 6개의 크기에 <table> 하나를 넣는다.
      </table>
    </div>
    <div class="col-sm-6">
      <table class="table">
      </table>
    </div>
    <div class="col-sm-6">
      <table class="table">
      </table>
    </div>
    <div class="col-sm-6">
      <table class="table">
      </table>
    </div>
  </div>
</div>
```  


## table
[table](https://getbootstrap.com/docs/4.4/content/tables/)  

|Table|Tag|Mean|
|:--|:--|:--|
||`<table>`|table만드는 태그|
||`<tr>`|table의 행 만드는 태그|
||`<td>`|table의 열 만드는 태그|  

아래의 `html`소스를 보면서 bootstrap의 활용한 `<table>`태그를 작성하는 방법을 볼 수 있다.  



```html
<table class="table table-borderless table-hover">  borderless table , hover가능한 table
    <thead>                                       
        <tr>
            <td colspan="3" class="alert alert-info"><a href="">Menu1</a></td>  사용하는 열3개를 합친다. `alert-info`활용
        </tr>  
    </thead>                                                1개의 행에 3개의 열을 갖는 table 만드려 한다.
    <tbody>
        <tr>                                                <tr> 1개의 행
            <th scope="row">게시글123123123123123123</th>    <td> 1개의 열
            <td>작성자</td>
            <td class="text-right">                        ".text-right"는 글자의 우측정렬을 하게 한다.
                작성날짜
            </td>
        </tr>
        <tr>
            <th scope="row">게시글123123123123123123</th>
            <td>작성자</td>
            <td class="text-right">
                작성날짜
            </td>
        </tr>
        <tr>
            <th scope="row">게시글123123123123123123</th>
            <td>작성자</td>
            <td class="text-right">
                작성날짜
            </td>
        </tr>
        <tr>
            <th scope="row">게시글123123123123123123</th>
            <td>작성자</td>
            <td class="text-right">
                작성날짜
            </td>
        </tr>
    </tbody>
</table>
```  

## pagination  
다양한 게시물을 올리는 사이트를 보면 페이지이동 섹션이 있다. bootstrap에서는 이것을 도와주는 [pagination](https://getbootstrap.com/docs/4.4/components/pagination/) 이 있다.  

```html
<!-- pagination set -->
  <div class="black" style="height:30px"></div>          게시판 4개를 보여주는 container와 여백을 주기위한 <div>
  <ul class="pagination justify-content-center">         bootstrap의 pagination활용 justify-content-center를 활용한 중앙 정렬
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>  .page-item을 활용한 리스트
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
  <!-- pagination end -->
  ```  

## footer  
bootstrap은 footer에 대한 library는 없지만 다른 library를 활용하여 만들 수 있다. 아래에 빈 칸을 갖고 아래에 고정되는 footer을 만들고 싶다.  
```html
<footer class="d-flex justify-content-center align-items-end" style="height:10em;"> 
 class를 통해 display:flex적용 // justify-content-center 중앙 정렬 // align-items-end 수평정렬을 끝부분에 적용//
 height:10em을 통해 높이 설정  

  <div class="text-monospace">Copyright(c) 2020 Duckey.Kim all rights reserved. .text-monospace를 통해 폰트 변경
    <div class="text-center">                                                   .text-center를 통한 글자 중앙 정렬
      <a href="mailto:#">duckey-kdh@google.com</a>
    </div>
  </div>
</footer>
```