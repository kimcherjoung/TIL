```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    li.new::after/*이렇게 after,before같은 가상선택자를 사용하면 이부분만 앞,뒤에 효과를 줄수 있다*/{
        content: "new!";
        color: aqua;
        background-color: red;
        margin: 0px 3px;
        padding: 0px 2px;
        border-radius: 4px;
    }
</style>
<body>
    <div class="content">
        <h1>제품목록</h1>
        <ul>
            <li class="new">제품 A</li>
            <li>제품 B</li>
            <li>제품 C</li>
            <li class="new">제품 D</li>
        </ul>
    </div>
</body>
</html>```
