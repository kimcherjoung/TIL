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
        border-style: solid;/*none은 테두리가 없다 기본값임
                              hidden테두리를 감춥니다
                              solid는 실선으로 표시함
                              dotted는 점선으로 표시함
                              dashed는 테두리를 짧은 직선으로 표시함
                              double은 이중선으로  표시하고 border-width로 조절한다
                              groove는 창에 조각한것처럼 표시하고 홈이 파인들 입체느낌이 난다
                              inset는 border-collapse: seperate;일때는 전체 박스 테두리가 창에 박혀있는느낌이 나고 아니면 groove와 같다
                              outset는 border-collapse: seperater;일때는 전체 박스 테두리가 창에 튀어나온것처럼 표시되고 아니면 ridge와 같다
                              ridge는 테두리를 창에서 튀어나온 것처럼 표시됨*/

        border-width: 10px 4px 6px 8px ;/*box-width는 테두리의 두께를 조절한다
                                          앞서 배운 top,right,bottom,left순서는 여기서 쓰인다 오른쪽부터 순서대로 따로 조절할수 있고 한번에도 조절 가능하다*/

        border-color: blue;/*border-color는 테두리의 색을 고른다*/
    }
    .box2{
        width: 400px;
        height: 100px;
        border: solid 10px aqua;/*border를 이용해 속성,두께,색을 한번에 줄수있다*/
    }
    .box3{
        width: 400px;
        height: 100px;
        border: 3px solid;
        border-radius: 24px;/*border-radius는 테두리를 둥글게 만든다 입력하는건 테두리
                              img도 테두리를 둥글게 만들수 있다
                              top-left,top-right,bottom-left,bottom-right가 있어서 4곳을 다르게 둥글게 처리할수 있따*/
    }
</style>
<body>
    우선 박스모델은 top,right,bottom,left가 있는데 순서는 써진 그대로다
    테두리 스타일은 우선 border-style을 이용해 속성값을 주고 색상,두께를 지정해야 한다
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
</body>
</html>```
