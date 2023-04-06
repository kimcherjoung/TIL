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
        border: 1px solid;
        border-collapse: collapse;
    }
    th,td{
        border: 1px solid;
    }
</style>
<body>
    <table>
        <caption>선물용과 가정용 상품 구성</caption>
        <colgroup> <!--원하는 열에 스타일을 넣어줄려면 colgroup을 사용해 caption바로 뒤에 써준다-->
            <col style="background-color: #eee;">
            <col> <!--2번째 열에는 아무 스타일을 안넣어도 그냥 명시는 해줘야함-->
            <col style="width: 150px;">
            <col style="width: 150px">
        </colgroup>
        <thead> <!--thead,tbody,tfoot등 표는 세가지로 나뉘어져 분류할수 있다(thead는 머리부분임)-->
            <tr>
                <th>용도</th>
                <th>중량</th>
                <th>개수</th>
                <th>가격</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td  rowspan="2">선물용</td> 
                <td>3키로</td>
                <td>11~16개</td>
                <td>35000원</td>
            </tr>
            <tr>
                <td>5키로</td>
                <td>18~26개</td>
                <td>52000원</td>
            </tr>
            <tr>
                <td rowspan="2">가정용</td>
                <td>3키로</td>
                <td>11~16개</td>
                <td>30000원</td>
            </tr>
            <tr>
                <td>5키로</td>
                <td>18~26개</td>
                <td>47000원</td>
            </tr>
        </tbody>
    </table>
</body>
</html>```
