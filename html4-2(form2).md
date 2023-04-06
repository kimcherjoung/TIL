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
        <label for="memo">메모</label>
        <textarea cols="30" rows="3" id="memo"></textarea>
        <!--textarea는 여러줄을 입력하게 할수 있고 cols는 너비를 rows는 몇줄인지 정해준다-->
        <select size="1"><!--select는 선택할수 있는 드롭박스를 만듭니다-->
                         <!--size로 옵션을 몇개 보일건지 설정할수 있습니다-->
            <option value="g_3">선물용 3</option><!--option은 드롭박스에서 선택할 옵션들입니다-->
            <option value="g_5">선물용 5</option><!--value는 서버로 넘겨주는 값입니다-->
            <option value="f_3">가정용 3</option>
            <option value="f_5">가정용 5</option>
        </select>
        <input type="text" list="data">
        <datalist id="data"><!--datalist태그느 데이터목록을 만들어 바로 사용할 수 있게 합니다-->
            <option value="tjqj1">tjqj15</option>
            <option value="tjqj2">tjqj2</option>
        </datalist>
        <button type="submit">내용</button><!--button은 버튼을 만드는데 <input type="button">과 같고 type안에 내용을 실행함 submit은 서버에 전송,type을 안쓰면 submit으로 간주함-->
        <button type="reset">내용</button><!--type에 따라 입력한 내용을 재설정해 없애버림-->
        <button type="button">내용</button><!--그냥 버튼-->
    </form>
</body>
</html>```
