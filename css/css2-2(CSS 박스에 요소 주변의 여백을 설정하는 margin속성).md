```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    .margin1{
        /*margin은 요소주변의 여백을 의미하고 요소와 요소사이의 간격을 조절할수 있다 */
        width: 500px;
        height: 300px;
        margin: 50px;/*이건 4개 방향 으로 50px여백을 준것임*/
    }
    .margin2{
        width: 500px;
        height: 300px;
        margin: 30px 50px;/*이건 위아래 30px,양옆으로 50px여백을 준것임*/
    }
    .margin3{
        width: 500px;
        height: 300px;
        margin: 20px 30px 50px 60px;/*이건 순서대로 위20,오른쪽30,아래50,왼쪽60의 여백을 준것임*/
    }
    .ex{
        width: 600px;
        background-color: aqua;
        margin: 20px auto;/*좌우값을 auto로 해주면 자동으로 계산해 가운데 정렬을 할수 있다*/
    }
    /*참고로 위아래에 요소가 2개있고 둘다 margin을 30px로 준다 치면 총 margin이 60px로 나올것 같지만 둘중 더 큰값을 정해버려서 이런현상을 마진중첩이라한다
      위아래는 중첩이 되지만 옆에둘때에는 중첩이 되지 않는다*/
</style>
<body>
    <div class="margin1"></div>
    <div class="margin2"></div>
    <div class="margin3"></div>
    <div class="ex">
        <h1>예시...</h1>
        <p>예시.................</p>
        <p>dfasdf</p>
    </div>
</body>
</html>```
