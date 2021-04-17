# 프로젝트 설명

`Duck-Craft`프로젝트는 기획한 카테고리에 맞는 글또는 그림등이 포함된 글들을 게시하는 사이트이다. 그리고 첫 홈페이지에서는 각각의 카테고리에 대한 최신글 5개에 대한 정보를 보여준다(제목,작성자,일자). 그리고 그 정보를 선택하게 되면 database에 저장된 글을 보여주게 된다.

# Firebase-Cloud Firestore

User가 작성한 글들을 서버 자체에 저장하는 것이 아닌 Firebase의 Cloud Firestroe에 저장하기로 결정하였다.

### Firestore 의 특징

Cloud Firestore의 큰 특징이라고 하면 유연하고 확장 가능한 `NoSQL` 클라우드 데이터베이스를 사용하고 이 데이터들은 `Collection`-`document` 의 계층적 구조를 띈다. 데이터들을 `document`에 저장이 되고 데이터들을 저장하고 있는 `document` 는 `Collection` 에 저장이 된다. 결국 데이터들이 저장이 되는 곳은 `document` 이고 저장되는 형태는 `JSON`과 매우 비슷하다.  
<img src="/assets/images/structure-data.png" width="50%" height="50%">

### Firestore의 data 가져오기

Firestore의 data는 document에 저장이 된다. 그러면 data를 가져올때 data가 어떤 collection의 document에 저장이 되어있는지를 알아야한다. 나의 프로젝트에서는 "boards/category/posts/document"의 path로 저장을 하였다. collection은 boards,posts이고 document는 category,document들이 될것이다.
컬렉션이나 문서에 필드가 아닌 posts,822\*\*~같이 작성된 부분들은 colleciont.id, document의 id => doc.id가 된다.
![projectDataStructure](/assets/images/firestore-structure.png)
Example)) `category` gossip 의 posts를 가져온다고 가정한다면

```javascript
let gossipRef= db.collection("boards").doc("gossip").collection("posts")
//gossipRef를 만들어서 활용하여도 된다.
db.collection("boards")
    .doc("gossip")
    .collection("posts")
    .get()
    //posts의 문서들을 가져옴
    .then((snapshot) => {
      snapshot.forEach((doc)=>{
        console.log(doc.id +": =>"+doc.data())
            //각각의 posts id와 필드에 저장된 값들을 보여준다.
      });
    });
    .catch((err) => {
      console.log("Error getting documents", err);
    });
```

위의 코드로 가져오게 될 것이다. 이렇게 하면 만약 user가 요청한 카테고리에 대해서 데이터를 가져오는 것은 어려운 부분이 아니게 된다. 하지만 `index.ejs` 에서 각각의 category의 최신글 5개의 정보를 보여주는 과정에서 어려움에 부딪혔다.

### index.ejs에서의 어려움

user가 나의 프로젝트 사이트에 처음 접속할때의 request는 `/`을 통해서 들어오게 된다. 그리고 이 요청을 통해 서버는 firestore의 data들을 가져와서 response로 index.ejs를 rendering 해줘야 한다. 홈페이지 접속할 때 user의 요청에는 category에 대한 정보가 없기때문에 그 정보는 firestore에서 가져와야 한다. 지금 기획한 category는 2개이지만 category가 추가가 되는 경우 firestore에서 category 에 대한 정보를 가져온 후에 다시 data를 가져오는 것을 모두 수동적으로 작성을 해야한다. 이것은 너무 비효율적이다.  
**생각한 방향**  
collection `boards`에서 get()을 하면 프로젝트에서 사용하는 category에 대한 정보를 가져올 수 있다. 그 정보를 얻은 후 category의 이름을 활용하여 `boards/category/posts/document`에 접근한다.

### 해결방법

```javascript
var contents = new Map();
var allBoardsRef = db.collection("boards");
allBoardsRef.get().then((snapshot) => {
  var count = 0;
  snapshot.forEach((doc) => {
    let name = doc.id; // 각각의 카테고리의 이름을 저장한다.
    myModules.getPostsFromBoard(allBoardsRef, name).then((posts) => {
      let p = []; // 각가의 카테고리의 이름으로 posts의 최신글 5개의 id 가져온다.
      posts.forEach((post) => {
        var data = post.data(); // 각각의 id를 통해 필드의 값을 가저와서 data에 저장
        myModules.timeToString(data);
        p.push(data);
        //postdata를 p에 넣는다.
      });
      contents.set(name, p);
      // content라는 json필드로 카테고리 이름 : postdata로 저장
      count++; // 하나의 category의 data를 다 가져오면 count 를 ++ 한다.
      if (count == snapshot.size) {
        myModules.renderPost(request, response, "boards/index", contents);
      }
    });
  });
});
```

### 사용중 느낀점

collection 과 document의 boards , gossip, humor 등 의 name들을 `.id`로 얻을 수 있다.  
한개의 document를 얻는 것은 쉬웠지만 여러개의 documents들을 얻을 때는 `forEach`문을 사용하여 document의 id를 얻은 후 `.data()`를 통해 데이터를 가져오는 것에 유의하여야 한다.
collection - document 구조에서 data는 **document** 에 저장한다는 것을 항상 기억해야 한다

<script src="https://gist.github.com/duckey-kim/e614a1117d7c48f9cf01992c5bee4da5.js"></script>

#firestore #cloudfirestore
