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
        <thead> <!--thead,tbody,tfoot등 표는 세가지로 나뉘어져 분류할수 있다(thead는 머리부분임)-->
            <tr>
                <th>용도</th>
                <th>중량</th>
                <th>개수</th>
                <th>가격</th>
            </tr>
        </thead>
        <tbody> <!--tbody는 표의 메인이다-->
            <tr>
                <td  rowspan="2">선물용</td> <!--rowspan은 행을 합치므로 위,아래를 합친다-->
                <td>3키로</td>
                <td>11~16개</td>
                <td>35000원</td>
            </tr>
            <tr> <!--행을 rowspan으로 합쳤으니 밑에는 셀을 3개만 적는다-->
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
            <tr> <!--여기도 rowspan으로 합쳐서 3개의 셀만납둠-->
                <td>5키로</td>
                <td>18~26개</td>
                <td>47000원</td>
            </tr>
        </tbody>
    </table>
</body>
</html>```
