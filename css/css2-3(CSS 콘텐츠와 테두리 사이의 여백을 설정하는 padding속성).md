```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    /*padding은 콘텐츠와 테두리사이의 공간의 여백을 말한다
      margin과는 위치의 차이만 있을뿐이라서 지정하는 방법은 둘이 거의 같습니다*/
      .padding1{
        width: 60px;
        height: 40px;
        padding: 20px;/*padding도 margin처럼 4방향전부 20px주는거임*/
      }
      .padding2{
        width: 60px;
        height: 40px;
        padding: 20px 30px;/*이것도 margin처럼 위,아래 20px 양옆 30px이다*/
      }
      .padding3{
        width: 60px;
        height: 40px;
        padding: 20px 30px 40px 50px;/*이것도 순서대로 위20,오른쪽30,아래40,왼쪽50이다*/
      }
</style>
<body>
    <div class="padding1"></div>
    <div class="padding2"></div>
    <div class="padding3"></div>
</body>
</html>```
