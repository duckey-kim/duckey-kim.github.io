# 상속(inheritance)  
CSS의 명령들이 조상,부모 요소로 부터  
자손,후손들에게도 넘어가게 된다.  
상속이 되는 속성들은 글자들을 작성하는데쓰는  
속성들이 상속이 된다.  
속성이 상속되지 않을때에는 inherit을 입력하여  
상속시킬수 있다. ex)```position : inherit;```  

```html
<style>
        .ecosystem {
            color: red;
            .ecosystem의 하위요소들인 animal,tiger등에
            상속되어 적용된 것을 알 수 있다.
        }
        
    </style>

    <div class=ecosystem>
        <div class="animal">동물
            <div class="tiger">호랑이</div>
            <div class="lion">사자</div>
            <div class="elephant"></div>
        </div>
        <div class="plant">식물
            <div class="rose">장미</div>

        </div>
    </div>
```  
<style>
        .ecosystem {
            color: red;
        }
    </style>
<body>
    <div class="ecosystem">
        <div class="animal">동물
            <div class="tiger">호랑이</div>
            <div class="lion">사자</div>
            <div class="elephant"></div>
        </div>
        <div class="plant">식물
            <div class="rose">장미</div>
        </div>
    </div>
</body>