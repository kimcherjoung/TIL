```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    .choice{
        font-family: "맑은 고딕",돋움,굴림;
        /*font-family로 글꼴을 정할수 있고 글꼴이 없을수도 있으니 2,3개정도 더 생각해 적어 놓아야한다*/
    }
    .keyword{
        font-size: xx-small;
        /*정해진 키워드로 할수있다 크기는 xx-small<x-small<small<medium<large<x-large<xx-large 순이다*/
    }
    .word{
        font-size: 40px;
        /*단위는 em,rem,ex,px,pt등이있고 요즘은 상대적으로 크기가 바뀌는 em,rem을 많이 사용함*/
    }
    .percent{
        font-size: 300%;
        /*부모요소의 글꼴크기의 비례한다 font-size:30px;이렇게 지정하고 백분율을 쓰면 여기에 맞춰진다.그냥 백분율만 쓰면 기본크기에 비례한다*/
    }
    .italic{
        font-style: italic;/*이탤릭체로 표기할대 font-style속성을 이용함*/
    }
    .reser{
        font-weight: bold;/*normal(400),bold(700),border(더 굵게),lighter(더 얇게)등이 있다*/
    }
    .num{
        font-weight: 900;/*숫자로는 100에서 900까지 굵기를 정할수 있다*/
    }
</style>
<body>
    <p class="choice">글꼴 정하기</p>
    <p class="keyword">키워드 이용 글씨크기 조절</p>
    <p class="word">단위 이용 글씨크기 조절</p>
    <p class="percent">백분율 이용 글씨크기 조절</p>
    <p class="italic">이탤릭체로 표기할때 사용하는 속성</p>
    <p class="reser">예약어로 글자 굵기정하기</p>
    <p class="num">숫자로 글자 굵기정하기</p>
</body>
</html>```
