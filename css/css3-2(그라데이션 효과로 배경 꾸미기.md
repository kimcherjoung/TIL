```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    #back{
        background: linear-gradient(to top right, blue,white);
        /*linear-gradient는 순서대로 to에 최대 2개 방향을 적어 예를 들어 to top하나만 적으면 아래에서 위로 이렇게 하고
          두개를 적어서 to top right는 오른쪽 위로 그라데이션 효과가 나타난다는 겄이다.
          그리고 색을 2개 적어 무슨색에서 무슨색으로 퍼지게 할지 선택하면 된다*/
        width: 300px;
        height: 200px;
    }
    #back2{
        background: linear-gradient(45deg,red,white);
        /*그리고 to 방향,방향대신에 deg란 단어를 써 0~360의 각도를 이용할수 있다 */
        width: 300px;
        height: 200px;
    }
    #back3{
        background: linear-gradient(45deg,blue,10%,red);
        /*%를 이용해 어디부분에서 색이 바뀔건지 색상 중지점을 정해주면 된다*/
        width: 300px;
        height: 200px;
    }
    #back4{
        width: 300px;
        height: 200px;
        background: radial-gradient(closest-side,white,aqua,blue);
        /*radial-gradient함수를 이용해 모양,색들을 정해 원형 그데이션*/
    }
    #back5{
        width: 300px;
        height: 200px;
        background: radial-gradient(circle at 30% 20%,white,blue);
        /*at을 이용해 %로 가로,세로 값을 주면 그라데이션이 사작하는 원의 중심의 위치를 조절할수 있다*/
    }
    #back6{
        width: 300px;
        height: 200px;
        background: radial-gradient(yellow,white 20%,orange 50%);
        /*%로 어디에서 색이 바뀔건지 색상 중지점을 정해주면 된다*/
    }
    #back7{
        width: 300px;
        height: 200px;
        background: repeating-linear-gradient(white,#ccc 10%);
        /*repeating을 앞에 붙여주고 색상,크기를 정해주면 반복한다*/
    }
    #back8{
        width: 300px;
        height: 200px;
        background: repeating-radial-gradient(circle,white,aqua 20%);
    }
    #back9{
        width: 300px;
        height: 200px;
        background: repeating-linear-gradient(white,white 20px,blue 20px, blue 40px);
        /*반복할때 어색할때는 시작색크기,킅색크기를 정해주면 명확해진다*/
    }
</style>
<body>
    <div id="back"></div>
    <div id="back2"></div>
    <div id="back3"></div>
    <div id="back4"></div>
    <div id="back5"></div>
    <div id="back6"></div>
    <div id="back7"></div>
    <div id="back8"></div>
    <div id="back9"></div>
</body>
</html>```
