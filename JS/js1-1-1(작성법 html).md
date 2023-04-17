```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1 id="heading">자바스크립트</h1>
    <p id="text">위 텍스트 클릭해보든지</p>
    <script>//간단한 js문은 script를 이용해 바로 쓸수 있다
        var heading = document.querySelector('#heading');
        heading.onclick = function(){
            heading.style.color = "red";
        }
        </script>
    <h1 id="heading2">자바스크립트2</h1>
    <p id="text2">위 텍스트도 클릭해보든지</p>
    <script src="js1(작성법).js"></script><!--css처럼 외부파일로 불러올수도 있다-->
</body>
</html>```
