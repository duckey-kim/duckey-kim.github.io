```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>컨텐츠 구분 예제</title>
    <link rel="stylesheet" href="./main.css">


</head>

<body>

    <header>


        <nav>
            <ul>
                <li></li>
                <li></li>
                <li></li>
            </ul>

        </nav>



    </header>
    
    <main>
        <section>
            <h1>section</h1>
    
    
            <article>
                <h2>Article1</h2>
                <p>Contents...</p>
            </article>
            <h2>Article2</h2>
            <p>Contents...</p>
            </article>
            <h2>Article3</h2>
            <p>Contents...</p>
            </article>
    
    
        </section>
        <aside>
            Aside
        </aside>
    </main>

    <footer>
        <address>
            <a href="mailto:duckey.kim@gmail.com">duckey.kim@gmail.com</a>
            <a href="tel:+821012345678">01012345678</a>
        </address>
    </footer>
</body>

</html>
```


```css
header{
background: tomato;
margin: 10px;
padding: 20px;

}

header nav {


}


header nav ul {
display: flex;

}


header nav ul li {

list-style-type: none;
margin: 10px;
}
main {

    display: flex;
}
section {
width: 70%;
background: tomato;
margin: 10px;
padding: 10px;
box-sizing: border-box;

}

section h1 {



}


article {

background: yellowgreen;
margin-bottom: 10px;
padding: 10px;

}

article h2 {



}

article p {

}

aside {
width: 30%;
background: tomato;
margin: 10px;
padding: 20px;
box-sizing:border-box;


}

footer {
background: tomato;
margin: 10px;
padding: 20px;


}
footer address {


}

footer address a {
    display: block;
}
```
## 이용한 CSS이유!?  
1. box-sizing:border-box   
padding을 이용할 시 padding을 사용한 태그때문에  
위의 태그의 크기가 변하게 되는데 그것을 막는다.  
2. fotter에서 display: block  
footer에서 외부링크 **a**태그에서  
2개의 태그를 사용하였는데 **a**링크는 인라인 요소라서  
수평으로 나오기때문에 display:block을 사용하여 수직으로 나오게 변경.  
3. article의 선택자 선언  
article은 html의 구조안에서 보면 section의 하위요소라고 볼 수도 있지만  
article은 독립성을 띄고 있기 때문에 section의 하위요소가 아닌  
독립적인 태그로 선택자를 지정하였다.  
4. 선택자 선언  
HTML의 구조를 보고 header의 nav, header의 nav안에 ul등을  
아래처럼 표현하였다.

```css 
header{

}
header nav{

}
header nav ul{

}
```  
5. display: flex  
수직으로 나오는 태그들을 수평적으로 나오게 바꿔주는 속성값을 바꾸어 준 것  
이것은 좀 더 나중에 자세히 배울 예정


5. aside의 위치  
aside는 광고,배너등이 따는 구역을 뜻하는 태그이다.
그러나 section의 옆에 aside를 구현하고 싶지만  
html의 구조를 구성하는 태그들은 block요소이기때문에  
수직적으로 표현이 된다. section과 aside의 가로가 100%로 맞기때문에  
div의 태그로 묶은다음 display을 flex하면 해결이 되지만  
div보다는 의미가 있는 main이라는 태그를 사용하여 wrap하였다.
![aside (2020_02_23 12_36_37 UTC)](https://user-images.githubusercontent.com/57125670/76056375-c102dc00-5fb9-11ea-873f-887a2206b452.png)


