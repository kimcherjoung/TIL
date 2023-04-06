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
        border-collapse: collapse; /*table,td,th로 테두리를 주면 빈칸이 생기는데 그걸 없애줌 */
    }
    td,th{
        border: 1px solid;
    }
</style>
<body>
    <table> <!--표의 시작과 끝에 있는 태그이다-->
        <caption></caption> <!--표의 제목을 붙일때 사용하고 제목은 표의 위쪽 중앙에 표시됩니다-->
        <tr> <!--tr은 행을 만든다-->
            <th>1행 1열</th> <!--th는 진하게표시되 눈에 띄게 만든다-->
            <td>1행 2열</td> <!--td는 tr안에 쓰며 열을 추가한다-->
        </tr>
        <tr>
            <td>2행 1열</td>
            <td>2행 2열</td>
        </tr>
    </table>
</body>
</html>```
