```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    .jinsu{
        color: #f08032;/*16진수로 색을 나타낼수 있다*/
    }
    .eng{
        color: aqua;/*영어로 나타낼수 있다*/
    }
    .rgb{
        color: rgb(100, 0, 225);/*왼쪽부터 빨간색,초록색,파란색으로 숫자가 곧 색의 양과 비슷하다*/
    }
    .rgba{
        color: rgba(0, 0, 0, 0.5);/*맨오른쪽에서 투명도조절이 가능하고 1~0사이로 조절하면돼*/
    }
    .text{
        text-align: start;
        /*start는 현재 텍스트 줄의 시작 위치에 맞추어 문단을 정렬합니다
          end는 현재 텍스트 줄의 끝 위치에 맞추어 문단을 정렬합니다
          left는 왼쪽에 맞추어 문단을 정렬합니다
          right는 오른쪽에 맞추어 문단을 정렬합니다
          center는 가운데에 맞추어 문단을 정렬합니다*/
    }
    .height{
        line-height: 24px; 
        /*24px만큼 줄 간격을 지정해준다
          line-height: 2.0;이렇게면 문단의 글자크기의 2배만큼 줄간격이 생긴다
          line-height: 200%;이렇게 해도 문단의 글자크기의 2배만큼 줄간격이 생긴다
          줄간격은 만약 텍스트가 가운데정렬이 되었는데 세로로 정렬이 안되있을때 사용할수 있다*/
    }
    .middle{
        text-decoration: none;/*none은 하이퍼링크를 사용하면 밑줄이 생기는데 이걸로 없앨수 있다*/
    }
    .under{
        text-decoration: underline;/*underline은 밑줄을 표시해준다*/
    }
    .up{
        text-decoration: overline;/*overline은 윗줄을 표시한다*/
    }
    .shadow{
        text-shadow: 3px 3px 4px black;/*왼쪽부터 순서대로 텍스트로부터 그림자까지의 가로길이,세로길이,그림자 번짐정도,색상입니다*/
    }
    .abc{
        text-transform: capitalize;/*text-transform은 대소문자를 변형한다
                                     capitalize는 첫번째 글자를 대문자로 바꾼다
                                     uppercase는 모든 글자를 대문자로 변형한다
                                     lowercase는 모든 글자를 소문자로 변환한다
                                     full-width는 가능한 모든문자를 전각문자로 변환하는데 전각문자는 가로와 세로의 길이비율이 같은 글자이다*/
    }
    .blank{
        letter-spacing: 0.3em;/*letter-spacine은 글자와 글자사이의 간격을 조절하고 em,px나 퍼센트로 조절함
                                word-spacing속성은 단어와 단어사이간격ㅇㄹ 조절하는데 css에선 letter-spacing을 주로 사용함*/
    }
</style>
<body>
    <p class="jinsu">16진수로 색표현하기</p>
    <p class="eng">영문법으로 색표현하기</p>
    <p class="rgb">rgb로 표현하기</p>
    <p class="rgba">rgba로 투명도까지 표현하기</p>
    <p class="text">텍스트를 정렬하기<br>텍스트를 정렬하기2</p>
    <p class="height">텍스트 줄 간격조절하기</p>
    <p class="middle">텍스트에 줄을 표시 안함</p>
    <p class="under">텍스트 아래에 밑줄 표시</p>
    <p class="up">텍스트 위에 윗줄 표시</p>
    <p class="shadow">텍스트에 그림자 효과주기</p>
    <p class="abc">텍스트의 대소문자를 변형 html</p>
    <p class="blank">글자 간격 조절 하기</p>
</body>
</html>```
