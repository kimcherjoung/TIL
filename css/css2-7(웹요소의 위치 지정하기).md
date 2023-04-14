```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    #pos1{
        width: 300px;
        position: absolute;
        left: 50px;
    }
    #pos2{
        width: 300px;
        position: absolute;
        right: 50px;
    }
    #pos3{
        width: 300px;
        position: absolute;
        left: 400px;
        top: 50px    }
    #pos4{
        width: 300px;
        position: absolute;
        bottom: 50px;
    }
</style>
<body>
    position은 static,relative,absolute,fixed가 있고 이걸 이용해 밑네 4개를 이용해 위치를 조절할수 있다
    static은 문서에 흐름에 맞처 배치하는 기본값임
    relative는 위칫값을 지정할수 있단걸 빼면 static과 같음
    absolute는 relative값을 사용한 상위 요소를 기준으로 위치를 지정
    fixed는 브라우저 창을 기준으로 위치를 지정해 고정해버림
    <br>
    우선 위치하기전 알아야 할 속성
    left는 기준 위치와 요소사이에 왼쪽으로 얼마나 떨어져 있는지 지정
    right는 기준 위치와 요소사이에 오른쪽으로 얼마나 떨어져 있ㄴ느지 지정
    top은 기준 위치와 요소사이에 위쪽으로 얼마나 떨어져 있는지 지정
    bottom은 기준 위치와 요쇼 사이에 아래쪽으로 얼마나 떨어져있는지 지정
    <p id="pos1">(left 사용시)Lorem ipsum, dolor sit amet consectetur adipisicing elit. Esse, recusandae temporibus voluptatum quam deserunt quidem provident. Odit, earum alias. Quos, aspernatur esse debitis quis doloribus voluptate dolorum. Possimus, vel reprehenderit.</p>
    <p id="pos2">(right 사용시)Lorem ipsum, dolor sit amet consectetur adipisicing elit. Non enim eveniet consequuntur porro, optio sapiente doloribus veritatis distinctio dolorum laborum repellat! Magnam ducimus eius qui! Recusandae et tempora sequi voluptatibus.</p>
    <p id="pos3">(top 사용시)Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi, quod blanditiis illum, odit temporibus facere pariatur quidem qui soluta debitis natus tenetur eum reprehenderit sit est impedit delectus, molestiae vero.</p>
    <p id="pos4">(bottom 사용시)Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam eum nulla odit aperiam praesentium, quas consequatur tempore unde, laudantium nihil, quo porro culpa excepturi iste molestiae. Dolorum, illo! Odit, minus?</p>
</body>
</html>```
