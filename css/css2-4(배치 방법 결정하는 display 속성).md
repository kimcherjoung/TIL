```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    .box1{
        width: 60px;
        height: 40px;
        background-color: aqua;
        display: inline;/*display는 블록 레벨요소를 인라인요소로 바꿀수도 인라인요소를 블록 레벨요소로 바꿀수 있다
                          원래 div는 블록 레벨 요소라 다른 div가 옆에 못왔으나 display: inline을 줘소 옆에 올수 있게 할수 있다
                          display: inline;은 블록 레벨요소를 인라인으로 바꿔 옆에 올 수 있게 하고
                          display: block;은 인라인요소를 블록 레벨요소로 바꿔 옆에 못 올 수 있게 하고
                          display: inline-block은 인라인,블록 레벨요소의 속성을 모두 가지고 마진과 패딩을 지정할수 있다
                          display: none;은 요소를 화면에 아예 표시하지 않는다*/
    }
    .box2{
        width: 60px;
        height: 40px;
        background-color: aqua;
        display: inline;
    }
    ul{
        list-style: none;
    }
    li{
        display: inline-block;/*이렇게 inline-block속성값을 주면 div가 원랜 margin,padding값으 주지 못했지만 이제 줄수있게 된다*/
        padding: 20px;
        margin: 0px 20px;
        border: 3px solid;
    }
</style>
<body>
    <div class="box1">box1</div>
    <div class="box2">box2</div>

    <ul>
        <li>menu1</li>
        <li>menu2</li>
        <li>menu3</li>
        <li>menu4</li>
    </ul>
</body>
</html>```
