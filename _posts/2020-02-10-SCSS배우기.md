# SCSS 배우기  

CSS는 선택자를 과용하고 연산기능의 한계 구문의 부재등 단점이 있다.  
웹에서는 표준 css로 동작하기때문에 다른 선택권이 없다.  

## CSS Preprocessor  
Sass,Less등 `전`처리기 를 활용하여 단점을 보완한 후 컴파일 해서 css처럼 사용할 수 있다.  

## Sass와 SCSS의 차이점  
안에 들어가는 내용은 같지만 문법이 조금 다르다.  
SCSS는 CSS의 문법과 비슷하다. 중괄호와 세미콜론이 있다.  Sass는 중괄호와 세미클론이 없다.  


## 문법 Syntax  
CSS 주석은 /*...*/ 이다  
Sass/SCSS는 두가지 스타일의 주석을 사용한다.  
```scss
// 컴파일되지 않는 주석   메모로 남길필요없을때 사용
/* 컴파일 되는 주석 */    메모로 남길때 사용
```

Sass의 여러줄 주석 의 특징
```scss
/* 컴파일 되는
* 여러줄 
* 주석 */
```  

## 데이터 종류  
|데이터|설명|예시|
|:--|:--|:--|
|`lists`|공백이나 ,로 구분된 값의 목록 |`(apple,orange)`,`apple orange`|
|`Maps`|lists와 유사하나 `Key:value`형태 |`(apple:a,orange:b)`|

### 특이사항  
Sass에서 사용하는 데이터 종류들의 몇 가지 특이사항  
 1. Number: 숫자에 단위가 있거나 없을 수 있다. 
 2. String: 문자에 `"`가 있을수 있거나 없을 수 있다.  
 3. Bulls: 속성값으로 `Null`이 사용되면 컴파일 하지 않는다.  
 4. Lists: `()`를 붙이거나 안 붙일 수 있다.  
 5. Maps: `()`를 꼭 붙여야 한다.

## nesting  

CSS를 활용하여 웹페이즈등을 만들 때의 문법을 보자.  
```css
.leftcontainer{
    width:100px;
}
.leftcontainer .menu{
    margin:10px;
}
.leftcontainer .menu li{
    list-style:none;
}
```
위에 처럼 명시해야 하는 `descendant selecter`들이 많아지게 된다. 하지만 SCSS의 중첩을 활용하면 쉽게 할 수 있다.

```scss
.leftcontainer{
    width:100px;
    .menu{
        margin:10px;
        li{
            list-style:none;
        }
    }
}
```  
SCSS의 중첩을 활용하면 불필요한 중첩 선택자들을 적을 필요가 없다.  

## Ampersand (상위선택자 참조)  
중첩 안에서 `&` 키워드는 상위의 선택자를 참조하여 치환한다.  

```scss
.btn{
    position:absolute;
    &.active{     이 위치에서의 상위선택자는 btn 
        color:red;
    }
}
```  
Compile
```css
.btn{
    position:absolute;
}
.btn.active{    .btn 이고 .active 인것을 찾는다.
    color:red;
}
```  

## @at-root (중첩 벗어나기)  
변수를 사용하였을 때 변수는 `$`을 통해 선언할 수 있다.  
**단!** 변수는 선언한 영역에 중첩된 부위에서 사용할 수 있다. 만약에 선언한 중첩이 아닌 다른 범위에서 사용하고 싶을 때 `@at-root`을 활용하여 중첩에서 만들면 중첩이 아닌 다른 범위에서 사용할 수 있다.  

```scss
li{
    $w:100px;   변수 선언
    $h:100px;
    .item{
        width:$w;
        height:$h;
    }
    @at-root .box{  올바른 선언!
        width:$w;   li태그 중첩안에서 선언된 변수를 사용하지만 중첩외에서 사용을 원한다.
        height:$h;  실제로는 li태그에서 선언되었지만 .box는 li의 태그 밖에서 사용된다.
    } 
}
```  

*Compile*  
```css
li .item{
    width:100px;
    height:100px;
}
.box{            li태그의 중첩이 아닌 중첩 밖에서 변수의 값을 활용한다.
    width:100px;
    height:100px;
}
```  

## 중첩된 속성  
`font-` `margin-`등과 같이 동일한 이름을 가지는 속성들을 중첩을 사용하여 부여할 수 있다.  
`xxx:{} `을 활용한다.  

```scss
.box{
    font: {
        weight:bold;
        size:10px;
        family:sans-serif;
    };
    margin: {
        top:20px;
        bottom:20px;
    };
    padding: {
        bottom:40px;
        right:30px;
    };
}
```  

## variable 
반복적으로 사용되는 값을 `variable`로 지정할 수 있다.  
변수 이름 앞에는 항상 `$`를 붙여야 한다.  
```$valiable:value;``` 의 형태를 띈다.  

**SCSS**  
```scss
$color-primary:#e96900;
$url-images:"/assets/images/";
$w: 200px;

.box{
    width:$w;
    margin-left:$w;
    background: $color-primary url($url-images + "bg.jpg")
}
```  
*Compile*  
```css
.box {
  width: 200px;
  margin-left: 200px;
  background: #e96900 url("/assets/images/bg.jpg");
}
```  

## Variable Scope  
Variable은 사용가능한 Scope가 있다.  
선언된 블록 `{}` 안에서난 사용가능하다.  

## Variable Reassignment  
variable을 다른 variable에 적용할 수 있다.  

## global  
`!global`을 활용하면 variable의 scope를 global로 설정할 수 있다.  
즉 설정된 블록`{}`이 아닌 전역에서 사용할 수 있다.  

```scss
.box{
  $w:100px !global;
  width:$w;
  .items{
    $w:200px;               .box .items 에서 variable 재선언
    width:$w;
  }
}

.container{
  width:$w;
}
```  
*Compile*  
```css
.box {
  width: 100px;
}
.box .items {
  width: 200px;            .box .items 에서 재선언 값이 들어와 있다.
}

.container {
  width: 100px;             global variable의 value값이 들어와있다.
}   
```  

## default  
`!default` 할당되지 않은 variable의 초깃값을 설정한다.  
할당된 variable에 사용된다면 `!default`한 값은 무시된다.  
사용하는 이유는 이미 할당된 변수에 변화를 주지 않기 위해서 이다.  

```scss
$color-primary:red;
.box{
    $color-primary:blue !default;       이미 할당된 variable
    background:$color-primary;
}
```  
*compile*
```css
.box {
  background: red;        !default 를 무시하고 red 가 된것을 알 수 있다.
}
```  

## 문자 보관  
`#{}`를 활용한다. 코드의 어디든지 variable값을 사용할 수 있다.  
```scss
$family:unquote("Droid+Sans");
@import url("http://fonts.googleapis.com/css?family=#{$family}");
```  
*Compile*  
```css
@import url("http://fonts.googleapis.com/css?family=Droid+Sans");
```  





