```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    table{
        border: 1px solid;/*border는 표에테두리를 만들어 준다*/
        caption-side: bottom;/*caption-side는 caption자리를 바닦에둔다 top이 있는데 이건 기본값*/
        border-spacing: 10px;/*border-spacing은 셀들 사이의 거리를 조절해줄수 있다 오른쪽부터 수평거리와 수직거리르 적어주면 되고 둘이 같으면 하나만 적어도 됨*/
        border-collapse: collapse;/*border-collapse는 셀사이의 공백을 없애버릴수 있다.*/
    }
    td,th{
        border: 1px solid;
        text-align: center;
        padding: 10px;
    }
</style>
<body>
    <table>
        <caption>예시 표</caption>
        <tr>
            <th>용도</th>
            <th>중량</th>
            <th>개수</th>
            <th>가격</th>
        </tr>
        <tr>
            <td rowspan="2">선물용</td>
            <td>3kg</td>
            <td>11~16과</td>
            <td>35000원</td>
        </tr>
        <tr>
            <td>5kg</td>
            <td>18~26과</td>
            <td>52000</td>
        </tr>
        <tr>
            <td rowspan="2">가정용</td>
            <td>3kg</td>
            <td>11~16과</td>
            <td>30000</td>
        </tr>
        <tr>
            <td>5kg</td>
            <td>18~26과</td>
            <td>47000</td>
        </tr>
    </table>
</body>
</html>```
