```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    body{
        height: 2000px;
        background-image: url(image/사막여우.jpg);
        /*background-image를 사용하고 url에 사진을 넣어 배경으로 사용가능하다*/
        background-repeat: no-repeat;
        /*background-repeat는 사진이 어떻게 반복할건지 나타낸다
          repeat는 기본값으로 세로,가로다 반복한다
          repeat-x는 브라우저화면이 가득찰때까지 가로로 반복한다
          repeat-y는 브라우저화면이 가득찰때까지 세로로 반복한다.
          no-repeat는 한번만 표시하고 반복하지 않는다*/
        background-position: center top;
        /*background-position은 순서대로 수평위치,수직위치를 left,top등 약속어나 백분율,길이 값을 줘서 조절헌다*/
    }
    #back{
        width: 300px;
        height: 200px;
        background-image: url(image/city.jfif);
        border: dotted 13px;
        background-origin: padding-box;
        /*background=clip처럼 패딩까지 아님 테두리까지 아님 전체를 적용할껀지 정하는 속성이다
          content-box는 기본값으로 내용까지만 배경이미지를 표시 기본값임
          padding-box는 패딩까지 배경이미지를 표시
          border-box는 테두리까지 배경이미지를 표시*/
    }
    #back2{
        background-image: url(image/사막여우.jpg);
        width: 300px;
        height: 200px;
        background-attachment: fixed;
        /*background-attachment를 fixed로 맞추면 배경이미지가 고정되 움직여도 사진이 따라 움직이지 않는다 해봐야 잘 안다*/
    }
    #back3{
        background-image: url(image/tree.jfif);
        width: 300px;
        height: 200px;
        background-size: contain;
        /*background-size배경의 크기를 조절한다
        contain은 요소안에 배경이미지가 다들어올수 있게 확대,축소한다
        cover는 배경이미지로 요소를 모두 덮도록 확대,축소한다
        px를 이용한 크기지정,백분율을 사용가능하다*/
    }
</style>
<body>
    <div id="back"></div>
    <div id="back2"></div>
    <div id="back3"></div>
</body>
</html>```
