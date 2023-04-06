```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <fieldset>
        <legend>반품 정보</legend>
        <p>만일 수령한 상품에 문제가 있다면 즉시 <strong>반품 신청</strong>해주세요</p>
        <p>반품 신청시 상품의 상태를 사진으로 첨부해주세요</p>
        <input type="file"><!--file은 파일을 첨부할수 있게된다-->
    </fieldset>
    <fieldset>
        <input type="hidden" value="사이트를 통한 직접 로그인"><!--hidden은 웹에선 보이지 않지만 value값을 서버로 전송이 됩니다-->
        <label>아이디: <input type="text"></label>
        <label>비밀번호: <input type="password"></label>
    </fieldset>
</body>
</html>```
