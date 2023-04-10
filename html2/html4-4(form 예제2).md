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
                    <label>아이디<input type="text" min="4" max="10" placeholder="4자~10자 사이 공백없이" autofocus></label>
                </li>
                <li>
                    <label>이메일<input type="email"></label>
                </li>
                <li>
                    <label>비밀번호<input type="password" placeholder="문자와 숫자, 특수 기호 포함"></label>
                </li>
                <li>
                    <label>비밀번호 확인<input type="password"></label>
                </li>
                <li>
                    <label id="guild">가입 경로</label>
                    <select id="guild">
                        <option value="blog">블로그</option>
                        <option value="search">검색</option>
                        <option value="sns">SNS</option>
                        <option value="guita">기타</option>
                    </select>
                </li>
                <li>
                    <label id="memo">메모</label>
                    <textarea cols="40" rows="4" placeholder="남길 말씀이 있다면 남겨주세요"></textarea>
                </li>        
            </ul>
        </fieldset>
        <fieldset>
            <legend>이벤트와 새로운 소식</legend>
            <label><input type="radio" value="on">메일 수신</label>
            <label><input type="radio" value="off" checked>매일 수신 안 함</label>
        </fieldset>
        <input type="submit" value="가입하기">
        <input type="reset" value="취소">
    </form>
</body>
</html>```
