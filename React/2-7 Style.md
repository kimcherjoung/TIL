#Style
>React에서  css를 사용하는 방법은 여러가지 가 있습니다  
>예를 들면 평범하게 css파일을 연결하는 방법과 그냥 써버리는 인라인 스타일링을 사용할수 있습니다. 하지만 React에선 더 다양한 css을 쓸 수 있게 해줍니다

## SASS(SCSS) 사용하기
>Sass(Scss)는 css 전처리기로 복잡한 작업을 쉽게 할 수 있도록 해 주고, 스타일 코드의 재활용성을 높여 줄 뿐만 아니라 코드의 가독성을 높여줘서 유지 보수를 쉽게 해줍니다  
>Sass에서는 두 가지 확장자 .scss와 .sass를 지원합니다. 이 두 개는 문법에서 약간의 차이가 있습니다  
sass
```scss
$font-stact: Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stact
  color: primary-color
```
scss
```scss
$font-stact: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stact;
  color: primary-color;
 }
```
>주요 차이점을 살펴보자면 .sass확장자는 중괄호({}) 와 세미클론(;)을 사용하지 않습니다  
>그래서 보통을 .scss를 자주 사용합니다
### Sass 추가하기
>sass를 사용하기 위해서는 
```yarn
$ yarn add sass
```
>를 사용해서 Sass를 추가해주어야 한다
