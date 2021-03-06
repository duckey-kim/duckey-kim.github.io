나의 Github에 공부한 일지를 올리려다보니  
일지작성을 HTML문법을 사용하였지만 일지작성에는  
Markdown문법이 간편하고 보기 편하다.  
그렇기때문에 Markdown 기본 문법을 알 필요를 느꼈다.

마크다운(MarkDown)에 대해서 알아보자
파일 확장자가 .md 로 된 파일과
웹 개발을 하면서 아마 README.md 라는 이름의 파일을 본 적이 있을 것이다.
이 파일이 마크다운 문법으로 작성된 파일이다.

# 마크다운의 장점

1. 문법이 쉽다.
2. 문법이 쉽기 때문에 관리또한 쉽다.
3. 지원 가능한 플랫폼과 프로그램이 다양하다.

# 마크다운의 단점
1. 표준이 없어 사용자마다 문법이 다 다르다.
2. 모드 HTML 마크업을 할수 없다.


제목 (Header)

# 제목 1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
###### 마지막 제목


강조
=====

 이텔릭체는 *별포* 또는 _언더바_ 를 사용한다.
 두껍게 하려면 **별표2개** 또는 __언더바2개__ 를 하면된다.

 **_이텔릭체_ 와 두껍게**   별표 2개로 두껍운 부분을 묶고 언더바로 이텔릭체를 부분 적용.

목록
=====

```
1. 순서가 필요한 목록
1. 순서가 필요한 목록
    - 순서 필요없는 서브 목록
    - 순서가 필요없는 서브 목록
1. 순서가 필요한 목록
    1. 순서가 필요한 서브 목록
    1. 순서가 필요한 서브 목록

1. 순서가 필요한 목록
    - 순서가 필요없는 서브목록 에 사용 가능한 기호
    - hypen
    * asterisks
    + plus sign
```





1. 순서가 필요한 목록
1. 순서가 필요한 목록
    - 순서 필요없는 서브 목록
    - 순서가 필요없는 서브 목록
1. 순서가 필요한 목록
    1. 순서가 필요한 서브 목록
    1. 순서가 필요한 서브 목록

1. 순서가 필요한 목록
    - 순서가 필요없는 서브목록 에 사용 가능한 기호
    - hypen
    * asterisks
    + plus sign



링크
-----

[google](https://google.com)

[NAVER](https://naver.com "링크 설명을 작성하세요.")

[Dribbble][Dribbble link]

[Github][1]  

```
[표시할이름](인터넷주소)

[표시할이름](인터넷주소 "마우스 대면 나오는 설명")

[표시할이름][1]

참조링크 사용법 [1]: 인터넷주소 "설명"
```
  
문서안에서 [참조링크]을 사용할 수 있다  
일반 URL이나 <>의 안의 url 자동 링크 된다.  
구글 홈페이지: https://google.com 

네이버 홈페이지 : <https://naver.com>


[Dribbble link]: https://dribbble.com
[1]: https://github.com
[참조링크]: https://naver.com "네이버로 갑니다."

이미지
-----
```<img>```로 변환됩니다.

링크와 비슷하지만 앞에 ! 가 붙는다

![대체 텍스트를 입력하세요!](http://www.gstatic.com/webp/gallery/5.jpg "링크 설명(title)을 작성하세요.")

![Kayak][logo]  

[logo]: http://www.gstatic.com/webp/gallery/5.jpg "To go Kayak"

이미지에 링크 걸기.
-----

링크를 생각 하면 쉽다. 링크는 a를 클릭하면 b라는 주소로 가는 구조이고    
**```[a](b)```**의 형태이다.  
이미지에 링크를 걸려면  ```[a]```를 이미지로 만들어주면 된다.  
이미지로 만들어주는 방법은 위에서 배운

**```![이름](이미지의주소)```**이기 때문에
이 구조를 다시 **```[]```** 로 묶어주면  
**```[!이름(이미지의주소)](링크의 주소)```**


# 이미지 & 링크 연습  

  
```
VS CODE 다운로드 : <https://code.visualstudio.com>

[VSCODE](https://code.visualstudio.com) 

[VSCODEDown][2]

[VSCODEDOWNLOAD]를 다운 받으면 된다.  

[![VScodedownload](https://upload.wikimedia.org/wikipedia/commons/9/9a/Visual_Studio_Code_1.35_icon.svg)](https://code.visualstudio.com)  

[VSCODEDOWNLOAD]: https://code.visualstudio.com "VScode 다운"  

[2]: https://code.visualstudio.com
```

VS CODE 다운로드 : <https://code.visualstudio.com>

[VSCODE](https://code.visualstudio.com) 

[VSCODEDown][2]

[VSCODEDOWNLOAD]를 다운 받으면 된다.  

[![VScodedownload](https://upload.wikimedia.org/wikipedia/commons/9/9a/Visual_Studio_Code_1.35_icon.svg)](https://code.visualstudio.com)  

[VSCODEDOWNLOAD]: https://code.visualstudio.com "VScode 다운"  

[2]: https://code.visualstudio.com 











