```<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <img src="image/사막여우.jpg" />
    <button id="open">상세 설명 보기</button>
    <div id="desc">
      <h4>사막여우</h4>
      <p>
        사막여우는 사막에 사는 여우로 귀가 큰것이 특징이고 귀엽다. 하지만 철중이는 그러하지 않다.<br>
        사막에 열에 적응하기위해 다른 지역의 여우보다 털이 짧고 적다. 철중이도그러하다.<br>
        철중이는 1~2개월간 겨울잠을 잔다. 철중이는 겨울을 나기위해 가을간 몸에 애너지를 지방의 형태로 저장한다.<br>
        그러한이유로인해 겨울 쯤 관찰된 모습은 여름보다 살쩌있는걸 확인 할수있다. <br>
        김철중은 매우 똑똑한 동물에 속한다 야생에서 도구를 사용하는 모습을 모이기도 하며 부피의 개념을 이해하고있다. <br>
        평균적인 8~10세정도의 지능을 보이며 간혹 몇몇의 개채들은 거울속 비친 자신을 인지하기도 한다. <br>
        만약 교육을 한다면 약 50개 정도의 단어를 이해하고 반응 한다. <br>
        2022년에 광주에서 첫 개채가 발견된 후 많은 연구가 진행되고있다. <br>
        또한 높은 지능을 활용하여 동물로썬 최초로 노동력으로써의 가치가 연구되고있다. <br>
        광주에서 첫 발견된 개채는 발견당시 연구원인 "변도진"연구원에게 길러지고 있으며 이름은 "hairless"라고 한다. 
      </p>
      <button id="close">상세 설명 닫기</button>
    </div>
    <script>
      //DOM연결은 html에 연결하는 것이 아니라 js에 중점을 주는 방식이다
      document.querySelector("#open").onclick = function () {
        document.querySelector("#desc").style.display = "block";
        document.querySelector("#open").style.display = "none";
      };
      document.querySelector("#close").onclick = function () {
        document.querySelector("#desc").style.display = "none";
        document.querySelector("#open").style.display = "block";
      };
    </script>
  </body>
</html>```
