```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    *{ /* *은 전체선택자로 모든 요소에 스타일을 넣습니다*/
        margin: 0;
    }
    p{ /* 태그를 이용해 태그요소를 꾸며줄수도 있다*/
        color: blue;
    }
    .class{ /*class는 특정구역에 스타일을 줄수있고 class2개를 이용해 한 요소에 2개이상 효과를 줄수 있다*/
        color: aqua;
    }
    .class2{
        font-style: italic;
    }
    #id{ /*id는 한번밖에 안됩니다*/
        color: brown;
    }
    #id2{
        font-style: italic;
    }
    h1,h2{ /*이렇게 2개를 동시해 주는 그룹선택자란 것도 사용할수 있다*/
        color: aqua;
    }
</style>
<body>
    <img src="image/사막여우.jpg">
    <p>스타일 넣을 요소</p>
    <p class="class class2">클래스 이용</p><!--class는 2가지를 줄수가 있다-->
    <p class="class">클래스 이용2</p>
    <p id="id">id이용</p>
    <p id="id2 id">id이용2</p><!--반면 id는 class와 다르게 여러개를 줄수가 없다-->
    <h1>h1</h1>
    <h2>h2</h2>
</body>
</html>```
