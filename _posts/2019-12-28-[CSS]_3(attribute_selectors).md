# 속성 선택자(Attribute Selectors)  
CSS의 속성은 property이다. 즉 HTML의 속성을 찾아서  
어떤 행위를 한다.  
## ATTR  
속성 ```[attr]```을 포함한 요소를 선택하겠다.  

## ATTR=VALUE  
속성```[attr=value]```을 갖고 value가 어떤 값인 것을 선택하겠다.  
```html
    <style>
    [type="password"] {
        type이 password 인것을 찾는다.
        opacity: 0.2;
        color: red;
    }
    </style>
<body>
<input type="text" value="duckhwan">
<input type="password" value="1234">
<input   type="text" value="disabled text" disabled>
</body>
```  
<style>
    [type="password"] {
        opacity: 0.2;
        color: red;
    }
    </style>

<body>    
<input type="text" value="duckhwan">
<input type="password" value="1234">
<input type="text" value="disabled text" disabled>
</body>  

## ATTR^=VALUE  
속성 ATTR를 포함하고 속성값이 VALUE로 시작하는 요소 선택!.  
## ATTR$=VALUE  
속성 ATTR를 포함하고 속성값이 VALUE로 끝나는 요소를 선택한다!.  
```html
<style>
    [class^="btn"] {
        속성이 class이고 class의 값의 시작이 'btn'인 것을 찾는다.
       border-radius: 50%;
       border: 1px solid black;
    }
    [class$="danger"]{
        속성의 값이 class이고 class의 마지막이 'danger'인 것을 찾는다.
        color: blueviolet;
    }
    [class$=success]{
        속성의 값이 class이고 그 값의 마지막이 'success'인 것을 찾는다.
        color: brown;
    }


    </style>
<body>
<button class="btn-success">Success</button>
<button class="btn-danger">Danger</button>
<button>Normal</button>
</body>
```
<style>
    [class^="btn"] {
        
       border-radius: 30%;
       border: 1px solid black;
    }
    [class$="danger"]{
        color: blueviolet;
    }
    [class$=success]{
        color: brown;
    }


    </style>
<body>
<button class="btn-success">Success</button>
<button class="btn-danger">Danger</button>
<button>Normal</button>
</body>