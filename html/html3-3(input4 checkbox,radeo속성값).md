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
        <legend>상품 선택</legend>
        <p>주문할 상품을 선택해라</p>
        <label>선물용 3KG<input type="checkbox" value="s_3" checked></label><!--value는 서버롤 보낼 값이다-->
        <label>선물용 5KG<input type="checkbox" value="s_5"></label>
        <label>가정용 3KG<input type="checkbox" value="h_3"></label>
        <label>가정용 5KG<input type="checkbox" value="h_5"></label>
        <p>포장 선택</p>
        <label>선물포장<input type="radio" value="yes"></label>
        <label>선물포장 안함<input type="radio" value="no"></label><!--checked는 미리 체그해 놓는것이다 속성값은 따로 없음-->
    </fieldset>
</body>
</html>```
