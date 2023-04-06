```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

<!--시멘틱태그는 웹사이트에서 어느부분인지 알수있게 해주는 태그이다-->

    <header> <!--header 태그는 말그로 헤더영역을 의미하고 주로 맨위쪽이나 왼쪽에 있고 주로 검색창이나 사이트메뉴를 삽입한다-->
				.........
        <nav> <!--nav 태그는 웹문서안에서 다른위치로 연결하는 링크를 만듭니다,네비게이션을 만들때 사용한다 -->
              <!--문서의 위치에 영향을 받지않고 보편적으로는 header, footer등에 있지만 따로 있을 수 있습니다-->
              <!--또한 nav 태그를 여러개 사용할때 id속성을 지정하면 각각 다른 스타일을 지정할 수 있습니다-->
        </nav>
    </header>

		<div> <!--div 태그는 시멘틱이 나오기전 사용한 태그이다 id, class속성을 사용해 문서 구조, 스타일을 적용할때 사용합니다-->
          <!--즉 영역을 구분할때나 스타일로 문서를 꾸미는 용도다-->
         <a href="#">fsadf</a>
    </div>

    <main> <!--main 태그는 핵심적인 내용을 담는것으로 문서당 1번씩만 쓸수있고 사이드바, 로고같이 모든 페이지에 들어가는건 넣을수 없다-->
           <!--웹페이지마다 달라지는 내용들을 구성한다-->
    </main>

    <article> <!--article 태그는 신문이나 잡지처럼 웹에서 실제로 보여주고 싶은내용을 넣는다-->
              <!--예를 들면 뉴스사이트의 기사처럼 독립된 웹 콘텐츠항목을 말한다-->
              <!--article안에는 section을 넣을수도 있다-->
				.........
        <section> <!--article과 비슷해보이지만 몇개의 콘첸츠를 묶는 용도일 뿐이다-->
                  <!--예를 들면 alticle은 블로그에 포스트자만 section 포스트안에 내용을 나눠 묶는것이다-->
        </section>
    </article>

    <aside> <!--aside는 본문내용외에 왼,오른,아래쪽등 사이드바를 만든다-->
            <!--웹사이트에서 필수는 아니므로 필요할때만 사용한다-->
    </aside>

    <footer> <!--footer 태그는 맨아래쪽을 나타내는 태그이다-->
             <!--웹사이트의 정보나, 저작권, 연락처등을 적는다-->
             <!--header, article, section같은 시멘틱태그를 사용할수 있다-->
    </footer>
</body>
</html>```
