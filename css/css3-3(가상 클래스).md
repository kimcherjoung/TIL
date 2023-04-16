```<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <style>
    ul {
      list-style-type: none;
      list-style: none;
    }
    li {
      padding: 20px;
      float: left;
      padding: 10px;
    }
    nav a:link, nav a:visited/*방문했던 링크와 안했던 링크의 스타일 지정*/ {
      text-decoration: none;
      color: black;
      font-size: 20px;
    }
    nav a:hover, nav a:focus/*마우스에 갔다대거나 초점을 맞췄을때 지정*/ {
      background-color: aqua;
      color: green;
    }
    nav a:active {
      background-color: red;
    }
    #intro:target/*target을 이용해 intro라는 위치로 링크할때 intro요소의 스타일을 바꾸고 싶을때 target선택자를 이용해 만들수 있다*/ {
      background-color: aqua;
      color: green;
    }
    textarea:disabled/*textarea에서 공지사항같이 disable속성이 적용되어 사용자가 수정을 못하는 상황에 맞춰 스타일을 변하게 할수 있다*/ {
      background-color: violet;
    }
  </style>
  <body>
    <nav>
      <ul>
        <li><a href="#">이용 안내</a></li>
        <li><a href="#">객실 소개</a></li>
        <li><a href="#">예약 하기</a></li>
        <li><a href="#intro">intro</a></li>
      </ul>
      <div id="intro">
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Iste
          assumenda autem eos asperiores libero sint! Necessitatibus, laboriosam
          maiores nemo, ad eius debitis minus modi facere ullam facilis dolorum
          repellat tenetur?
        </p>
      </div>
    </nav>
    <div id="div">
      <textarea disabled cols="40" rows="4">고객 개인정보 이용동의서</textarea>
    </div>
  </body>
</html>```
