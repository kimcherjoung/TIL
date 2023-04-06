```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <input type="number" min="1">min은 최솟값을 설정해준다 기본값은 0이다
    <input type="number" max="5">max는 최대값을 설정해준다
    <input type="number" step="2">한번 올리면 얼마나 올리는지 정한다 기본값은 1이다
    <input type="number" value="2">처음 들어가는 값을 정해줄수 있다
    <fieldset>
        <ul>
            <li>
                <label><input type="checkbox" value="s_3">선물용 3KG</label>
                <input type="number" min="0" max="5">개 (최대 5개)
            </li>
            <li>
                <label><input type="checkbox" value="s_5">선물용 5KG</label>
                <input type="number" min="0" max="3" value="1">개 (최대 3개)
            </li>
        </ul>
    </fieldset>
    <fieldset>
        <ul>
            <li>
                <label><input type="checkbox">가정용 3kg</label>
                <input type="range" min="0" max="5">개 (최대 5개)
            </li>
            <li>
                <label><input type="checkbox">가정용 5kg</label>
                <input type="range" min="0" max="3">개 (최대 3개)
            </li>
        </ul>
    </fieldset>
</body>
</html>```
