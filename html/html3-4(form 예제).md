```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form>
        <fieldset>
            <legend>사용자 정보</legend>
            <ul>
                <li>
                    <label id="uid">아이디</label>
                    <input type="text" id="uid">
                </li>
                <li>
                    <label id="email">이메일</label>
                    <input type="email" id="email">
                </li>
                <li>
                    <label id="pwd1">비밀번호</label>
                    <input type="password" id="pwd1">
                </li>
                <li>
                    <label id="pwd2">비밀번호 확인</label>
                    <input type="password" id="pw2">
                </li>
            </ul>
        </fieldset>
        <fieldset>
            <legend>이벤트</legend>
            <input type="radio" name="mailing" id="malling_y">
            <label for="malling_y">메일 수신</label>
            <input type="radio" name="mailing" id="mailing_n">
            <label for="mailing_n">메일 수신 안 함</label>
        </fieldset>
        <div id="buttons">
            <input type="submit" value="가입하기">
            <input type="reset" value="취소">
        </div>
    </form>
</body>
</html>```
