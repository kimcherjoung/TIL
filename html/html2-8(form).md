```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form action="register.php"><!--form은 로그인등 웹사이트에 정보를 보내는 곳이다,지금은 서버에 입력된 걸 전송하고 register.php를 실행한단 것이다-->
                                <!--form태그안에 여러 요소를 넣는것이 기본-->
                                <!--method속성은 get,post가 있다,name속성은 자바스크립트때 쓸 이름이다-->
                                <!--action속성은 내용을 처리해줄 서버프로그램을 지정함,target은 action속성에서 지정한 스크립트 파일을 다른 위치에서 열도록 함-->
    </form>
    <form action="" autocomplete="off"><!--autocomplete속성은 자동완성기는으로 평소엔 켜져있어 off를 사용해 꺼줄수 있습니다-->

    </form>
    <form action="">
        <fieldset> <!--fieldset은 하나의 폼안에서 구역을 나눠표시할때 사용하는 태그이다-->
            <legend>상품 선택</legend><!--legend태그는 field태그로 묶은 그룹에 제목을 붙힐수 있다-->
        </fieldset>
        <fieldset>
            <legend>배송 정보</legend>
            <label>배송지<input type="text"></label><!--label태그는 아이디처럼 입력란에 붙은 텍스트인 레이블을 붙일때 사용합니다.-->
            <label for="user-id">아이디(6글자 이상)</label>
            <input type="text" id="user-id"><!--이렇게 id를 이용해 둘이를 연결해줄수도 있습니다.-->
        </fieldset>
    </form>
</body>
</html>```
