```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    img{
        float: left;/*float은 웹요소를 왼쪽이나 오른쪽으로 이동해서 p태그는 원래 블로 레벨 요소라
                      이미지 옆에 올수 없지만 float을 이용해 이미지를 왼쪽이나 오른쪽으로 떠있게해 이미지 옆에 텍스트가 둘러싸게 할수 있다*/
        margin-right: 20px;
    }
    #box1{
        background-color: yellow;
        float: left;
        
    }
    #box2{
        background-color: aqua;
        float: left;
    }
    #box3{
        background-color: greenyellow;
        /*이렇게 위에서 float을 쓰고 나면 아무것도 안해도 요소가 float이 적용이 되어버려 left를 썻으면 clear: left; right를 썻으면 clearL right;를 써 평범한 박스로 다시 만들어 줄 수 있다*/
    }
    #box4{
        background-color: plum;
        clear: left;
    }
</style>
<body>
    <img src="image/tree.jfif">
    <p> Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum harum veniam quos. Voluptates repudiandae cum sit illo quia ipsum quasi ducimus quibusdam atque ipsa inventore praesentium, obcaecati incidunt doloremque dicta?
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos asperiores nesciunt harum sint consequuntur incidunt tenetur cumque dicta repellat, deleniti officia dolor reprehenderit et doloribus nemo dolores voluptatem cum illo!
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus omnis molestias est ipsa eius laudantium expedita, architecto corrupti accusamus. Illum eum doloremque eveniet dolorem iste eius, molestias atque. Doloremque, sequi!
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem aspernatur fuga cupiditate voluptate similique, sequi provident illo adipisci rerum doloremque minima excepturi, repellendus reiciendis fugiat reprehenderit. Sint deleniti id corporis!
    </p>
    <!--알아두든 모르든 상관없지만 아무말을 채우고 싶을때 문단을 만들고 lorem이라 치고 enter를 누르면 아무말이 나온다-->
    <div id="box1">box1</div>
    <div id="box2">box2</div>
    <div id="box3">box3</div>
    <div id="box4">box4</div>
</body>
</html>
```
