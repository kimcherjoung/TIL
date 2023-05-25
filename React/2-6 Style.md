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
## Sass 사용해보기
```scss
//변수 사용하기
$red: #fa5252;
$orange: #fd7e14;
$yellow: #fcc419;
$green: #40c057;
$blue: #339af0;
$indigo: #5c7cfa;
$violet: #7950f2;
//믹스인 만들기(재사용되는 스타일 블록을 함수처럼 사용할 수 있음)
@mixin square($size) {
    $calculated: 32px * $size;
    width: $calculated;
    height: $calculated;
}

.SassComponent {
    display: flex;
    .box { // 일반 CSS에서는 .SassComponent . box와 마찬가지다
        background: red;
        cursor: pointer;
        transition: all 0.3 ease-in;
        &.red{
            // .red 클래스가 .box와 함께 사용되었을 때
            background: $red;
            @include square(1);
        }
        &.orange {
            background: $orange;
            @include square(2);
        }
        &.yellow {
            background: $yellow;
            @include square(3);
        }
        &.green {
            background: $green;
            @include square(4);
        }
        &.blue {
            background: $blue;
            @include square(5);
        }
        &.indigo {
            background: $indigo;
            @include square(6);
        }
        &.violet {
            background: $violet;
            @include square(7);
        }
        &:hover{
            // .box에 마우스를 올렸을 때
            background: black;
        }
    }
}
```
```javascript
import React from "react";
import "./SassComponent.scss";

const SassComponent = () => {
  return (
    <div className="SassComponent">
      <div className="box red"></div>
      <div className="box orange"></div>
      <div className="box yellow"></div>
      <div className="box green"></div>
      <div className="box blue"></div>
      <div className="box indigo"></div>
      <div className="box violet"></div>
    </div>
  );
};

export default SassComponent;
```
>위에선 $를 이용해 변수를 설정해 줄수 있고  
>@mixin과 @include를 이용하면 함수와도 같이 사용할 수 있게 된다  
### utils 함수 분리하기
>여러 파일에서 사용될 수 있는 Sass 변수 및 믹스인은 다른 파일로 따로 분리하여 작성한 뒤 필요한 곳에서 쉽게 불러와 사용할 수 있습니다  
```scss
//변수 사용하기
$red: #fa5252;
$orange: #fd7e14;
$yellow: #fcc419;
$green: #40c057;
$blue: #339af0;
$indigo: #5c7cfa;
$violet: #7950f2;
//믹스인 만들기(재사용되는 스타일 블록을 함수처럼 사용할 수 있음)
@mixin square($size) {
    $calculated: 32px * $size;
    width: $calculated;
    height: $calculated;
}
```
```scss
@import './styles/utils';

.SassComponent {
    display: flex;
    .box { // 일반 CSS에서는 .SassComponent . box와 마찬가지다
        background: red;
        cursor: pointer;
        transition: all 0.3 ease-in;
        &.red{
            // .red 클래스가 .box와 함께 사용되었을 때
            background: $red;
            @include square(1);
        }
        &.orange {
            background: $orange;
            @include square(2);
        }
        &.yellow {
            background: $yellow;
            @include square(3);
        }
        &.green {
            background: $green;
            @include square(4);
        }
        &.blue {
            background: $blue;
            @include square(5);
        }
        &.indigo {
            background: $indigo;
            @include square(6);
        }
        &.violet {
            background: $violet;
            @include square(7);
        }
        &:hover{
            // .box에 마우스르 ㄹ올렸을 때
            background: black;
        }
    }
}
```
>미리 scss를 짜놓고 @import를 이용해 불러와 사용할 수 있습니다
## CSS Module
>Css Module은 CSS를 불러와서 사용할 때 클래스 이름을 고유한 값, 즉 [파일이름] _ [클래스 이름] _ [해시값] 형태로 자동으로 만들어서 컴포넌트 스타일 클래스 이름이 중첩되는 현상을 방지해 주는 기술입니다  
>원래는 설정을 별도로 해줘야 하지만 지금은 .module.css 확장자로 파일을 저장하기만 하면 CSS Module이 적용됩니다
```css
/*자동으로 고유해질 것이므로 흔히 사용되는 단어를 클래스 이름으로 마음대로 사용 가능*/

.wrapper {
    background: black;
    padding: 1rem;
    columns: white;
    font-size: 2rem;
}

/*클로벌 CSS를 작성하고 싶다면*/

:global .something {
    font-weight: 800;
    color: aqua;
}
```
```javascript
import React from "react";
import styles from "./CSSModule.module.css";

function CSSModule() {
  return (
    <div className={styles.wrapper}>
      안녕하세요, 저는 <span className="something">CSS Module!</span>
    </div>
  );
}

export default CSSModule;
```
>해당 클래스는 우리가 방금 만든 스타일을 직접 불러온 컴포넌트 내부에서만 작동하기에 흔한 이름으로 해도 상관없습니다  
>만약 특정 클래스가 웹 페이지에서 전역적으로 사용되는 경우라면 :global을 앞에 입력하여 글로벌CSS임을 명시해 줄 수 있습니다  
>CSS Module이 적욛도니 스타일 파일을 불러오면 객체를 하나 전달받게 되는데 CSS Module에서 사용한 클래스 이름과 해당 이름을 고유화한 값이 키-값으로 들어 있어서, console.log(styles)를 한다면 ```{wrapper: "CSSModule_wrapper_15bdQ"}```이렇게 결과가 나옵니다
  
>한번에 CSS Module 클래스를 여러개 사용하면 템플릿 리터럴 문법을 사용할수 있습니다
```javascript
import React from "react";
import styles from "./CSSModule.module.css";

function CSSModule() {
  return (
    <div className={`${styles.wrapper} ${styles.inverted}`}>
      안녕하세요, 저는 <span className="something">CSS Module!</span>
    </div>
  );
}

export default CSSModule;
```
>이렇게 하면 동시에 여러 클래스를 사용할 수 있게 됩니다
>또한 템플릿 리터럴 문법을 사용하기 싫다 하면
```javascript
className={[styles.wrapper, styles.inverted].join('')}
```
>이렇게 짜면 됩니다
