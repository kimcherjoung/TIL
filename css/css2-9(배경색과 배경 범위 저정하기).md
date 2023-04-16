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
        background-color: aqua;/*background-color는 배경색을 줄수 있다*/
    }
    #back{
        width: 300px;
        height: 200px;
        background-color: dodgerblue;
        background-clip: border-box;
        /*background-clip은 border-box,padding-box,content-box가 있다
          border-box는 테두리까지 모두 적용한다 기본값임
          padding-box는 박스 모델에서 테두리르 뺀 패딩까지 적용됨
          content-box는 padding제외 콘텐츠 부분만 적용됨*/
        border: dashed;
    }
</style>
<body>
    <div id="back">배경1</div>
</body>
</html>```
