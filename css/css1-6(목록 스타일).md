```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    .ex1{
        list-style-type: square;/*list-style-type은 순서없는목록앞에 다양한 불릿 모양을 넣을수 있고 
                                순서있는 목록엔 번호스타일을 지정할수 있다
                                disc는 기본형으로 채운 원 모양임
                                circle은 빈 원 모양임
                                square는 채운 사각형 모양임
                                decimal는 1부터 시작하는 10진수임
                                decimal-leading-zero는 앞에 0이붙는 10진수이다
                                lower-roman는 로마 숫자 소문자임
                                upper-roman는 로마 숫자 대문자임
                                lower-alpha또는 lower-latin은 알파벳소문자이다
                                upper-alpht또는 upper-latin은 알파벳대문자이다
                                none는 블릿이나 숫자를 없앰
                                이 속성들은 순서가 있든없든 다 사용할수 있음
                                */
    }
    .ex2{
        list-style-type: lower-roman;
    }
    .ex3{
        list-style-image: url(image/사막여우.jpg);
        /*list-style-image는 블릿을 이미지로 대체하는 것이다*/
    }
    .ex4{
        list-style-position: inside;
        /*list-style-postition은 들여쓰기가 되어 문단구별이 편해진다
        inside와 기본속성인 outside만 있다*/
    }
    .ex5{
        list-style: circle inside;
        /*list-style은 목록스타일을 한번에 줘소 코드를 간편화시킬수 있다*/
    }
</style>
<body>
    <h1>목록 예시</h1>
    <ul class="ex1">
        <li>예시1</li>
        <li>예시2</li>
        <li>예시3</li>
    </ul>
    <ol class="ex2">
        <li>예시1</li>
        <li>예시2</li>
        <li>예시3</li>
    </ol>
    <ul class="ex3">
        <li>예시1</li>
        <li>예시2</li>
        <li>예시3</li>
    </ul>
    <ul class="ex4">
        <li>예시1</li>
        <li>예시2</li>
        <li>예시3</li>
    </ul>
    <ul class="ex5">
        <li>예시1</li>
        <li>예시2</li>
        <li>예시3</li>
    </ul>
</body>
</html>```
