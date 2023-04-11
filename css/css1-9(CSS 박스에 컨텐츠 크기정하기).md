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
        width: 400px;
        height: 100px;
    }
    .box2{
        width: 50%;
        height: 100px;/*%를 사용하면 웹 브라우저 창에 따라 크기가 달라진다*/
    }
    .box3{
        box-sizing: border-box;/*box의 크기는 콘텐츠뿐만 아니라 테두리,패딩도 있어 계산하기 어렵다 이럴때 border-box로
                                 값을 주면 width,height를 사용할때 콘텐츠만 아니라 박스의 크기를 기준으로 해서 패딩,테두리까지 고려해 콘텐츠의 크기를 조절한다*/
        width: 400px;
        height: 100px;
    }
    .box4{
        box-shadow: -10px 12px 11px 1px;/*오른쪽부터 수평거리,수직거리,흐림정도,번짐정도,색을 쓴다 
                                          수평거린 양수는 오른쪽,음수는 왼쪽에 쓴다
                                          수직거린 양수는 아래쪽,음수는 위쪽에 쓴다
                                          마치 좌표처럼 어느 한쪽에만 그림자 효과가 나타난다 4선 전부 그림자 생기는것 불가능*/
        width: 400px;
        height: 100px;
    }
</style>
<body>
    콘텐츠 영역의 크기는 width,height로 정할수 있다.(단위인 px,em등 사용하거나,백분율 기준이다)
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
    <div class="box4"></div>
</body>
</html>```
