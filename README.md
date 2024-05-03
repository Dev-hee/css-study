# css(Cascading Style Sheet)
## CSS 작성 전 준비사항
* html 문서 준비(태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, style 으로 css파일 배치 
* ex) index.html, index.css
## CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부 스타일시트**
* html 파일 내에서 head태그 안에 style태그로 구분해서 작성하는 **내부 스타일시트**
* 외부 스타일시트 장점 :
- 장점 : 1대의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다.
* 내부 스타일시트 장점 : 
- 장점 : html 파일 내에 작성하여 태그와 한꺼번에 보기 편하다.
- 단점 : 2개이상의 html파일을 동시에 디자인관리하는 것이 불가능하다.
## CSS 선택자
* 1. 태그 선택자 :`<h1></h1>` -> `h1 {속성:값;}`
* 2. 클래스 선택자 : `<h1 class="a"></h1>` -> `.a{속성:값;}`
* 3. 아이디 선택자 : `<h1 id="b"></h1>` -> `#b{속성:값;}`
* 4. 자손 선택자 : `<h1><em><span></sapn></em></h1>` -> `h1 em span {속성:값;}`
* 5. 자식 선택자 : `<h1><em><em></em></em></h1>` -> `h1 >em {속성 값;}`
## CSS 디자인하기
* CSS 작성 전 HTML이 미리 디자인이 되어있으면 안된다.
* **HTML을 디자인 초기화하는 작업이 CSS 디자인 전 반드시 선행되어야 한다!!**
* 초기화 CSS : `reset.css` 공통파일(날짜나 프로젝트명 표기금지!)
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴(추천)을 연결 할 수 있다.
* "메인대표글꼴","후보글꼴"(후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다.
* 글꼴 이름에 한글이나 공백이 있으면 "(따옴표)" 가 필요하다. Noto+Sans+KR, 
 ex) font-family: "Noto Sans KR","맑은 고딕", sans-serif;
 ## font-size
 * 웹 글꼴 평균 16px
 * 사용 단위 px, %, em, rem
 * 절대값 : px, 상대값 : %, em, rem(권장)
 * rem (body(16)기준으로 계산해줌)
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1)
* 코드를 다 합쳤을 때 점수가 높은 쪽이 우선순위가 높다.
1. 다음 중 우선순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {}` 3+2+2+1=8  
* `#box #a .b p{}` 3+3+2+1=9     
* `#wrap #box .a{}` 3+3+2=8    
* `#wrap .a .b p{}` 3+2+2+1=8
2. 다음 중 우선순위가 가장 높고 낮은 선택자는?
* `#box #wrap .b p`  3+3+2+1 = 9
* `#box .b p` 3+2+1 = 6
* `#box .b` 3+2 = 5
* `#wrap .a .b .c p` 3+2+2+2+1 = 10
## color
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은색을 사용한다.
* aqua, lime, yellow, coral....
* 헥사코드 입력 최소값 0 ~ 최대값 F RGB코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #Hex #000000 == #000, #FF00CC => F0C
* rgba(red,green,blue,alpha) *최대색상 255
* alpha는 투명도를 줄 수 있다. ex) 1 (최대밝기)
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* `block` : 새로운 행, 크기, 여백 인식 / 너비100%와는 별도로 항상 줄바꿈이 이루어짐.
* `inline` : 내용만큼 크기 인식(그 외 크기인식 불가능)
* `inline-block` : 내용만큼 크기 인식(크기 추가설정가능), 옆으로 정렬
### box-sizing
* `box-sizing:border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 여백(padding)까지 포함해서 계산하는 속성
* 속성 미적용 시 : w100+h100+padding-top20 = 100x120
* 속성 적용 시 : W100+h100+padding-top20 = 100x100
### width, height
* 요소의 너비와 높이
* 절대값 px, 상대값 %, 화면 상대값 vw /*뷰 포트의 넓이*/, vh /*뷰 포트의 높이*/
* 상대값 처리는 0~100% 사이 값만 사용한다.

## form 요소와 속성
### `<form action="#" method=""> </form>`
* action : 입력된 정보를 제출하는 최종 주소(URL)은 action 속성에 입력합니다.
* method : 입력된 정보를 제출할 때 HTTP 정보를 method 속성에 입력합니다. 
* fieldset, legend : 
- 정보 컨트롤 요소 들을 용도에 맞게 그룹으로 묶을 경우 사용합니다.
- form의 자식 요소로 배치합니다.
- fieldset의 자식으로 배치합니다.

### `<input type="" name="">`
* type : checkbox, radio, option, select 등..
* name : 2개이상의 데이터를 묶어주는 그룹명
* readonly : 읽기전용 설정
* autofocus, autocomplete : 페이지 로딩 시 해당 컨트롤 자동 포커스 설정 / 검색창 자동완성
* value : 서버(action)전송 시 입력한 데이터 구분 명칭 / 미리 제시된 텍스트(활성화 시 제거안됨)
* placeholer :미리 제시된 텍스트(활성화 시 제거됨)
* value와 placeholder의 차이점 :
* maxlength : 최대글자 수 지정

### `<textarea></textarea>`
* rows, cols : 텍스트 영역의 세로 폭 / 텍스트 영역의 가로 폭
* 사용용도 및 주의사항 : 텍스트를 편집할 수 있는 컨트롤

### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접입력가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식 (데이터구분용), 선택양식(데이터구분 개별데이터X , 그룹데이터구분용)
* `value` : 입력양식(초기값), 선택양식(개별데이터구분용)

## css Layout
### float, flex
* `float` : 형제 관계에 해당하는 block or inline tag 왼쪽, 오른쪽 정렬할 때 사용
* 예 : ul-li *3개 정렬 `ul li {float:left;}`
* `flex` : 정렬하고자 하는 아이템의 부모한테 flex를 먼저 설정한다.
* 예 : ul-li *3개 정렬 `ul {display:flex;}`
* flex 설정 시 **기본값** : 메인축(수평) 교차축(수직)
* `display:flex` : 정렬대상의 부모 설정 속성값, 설정 시 해당 부모 기준 자식까지(자손X) flexible box layout 으로 처리하겠다.

## flex-direction : (container에 적용)
* container 안에 item의 메인축 방향을 설정할 때 사용
* flex-direction : row 왼쪽->오른쪽 수평축 (기본값)
* flex-direction : rpw-reverse 오른쪽 -> 왼쪽
* flex-direction:column 위-> 아래 수직축 변경
* flex-direction:column-reverse 아래->위

## flex-wrap : (container에 적용)
* flex-wrap:wrap 기본값(자동 줄바꿈)  ex) 1 2 3
* flex-wrap-reverse 행 기준 역방향으로 자동 줄바꿈 처리
* flex-wrap:nowrap 줄바꿈하지 않음(한 줄 처리) 가변너비에 따라 자동으로 % 크기 변경

## flex-flow : (container에 적용)
* flex-direction과 flex-wrap을 묶음으로 처리
* flex-direction: column + flex-wrap:nowrap 일 경우(아래)
* flex-flow:column nowrap 이라고 작성 가능.

## justify-content (container에 적용)
* container에 적용하는 속성
* 메인축의 정렬방법

## align-content (item 2줄 이상)
* 교차축의 아이템이 2줄 이상일 경우
* flex-wrap:wrap 적용한 상태로 확인하세요.
* align-content:stretch / align-content:flex-start / align-content:flex-end /align-content:center / align-content:space-between	/ align-content:space-around

## align-items (item 1줄)
* 교차축의 아이템이 1줄 일 경우 정렬방법
* align-items:stretch /align-items:flex-start /align-items:flex-end/ align-items:center /align-items:baseline

##  align-self (item에 적용하는 속성)
* item에 적용하는 속성.
* flex box의 교차축을 정렬.
* container에 적용하는 align-items보다 우선순위가 높습니다.
* align-self:flex-start / align-self:flex-end / align-self:center / align-self:baseline

## order (item에 적용하는 속성) (mobile 만들때 활용 많이 함.)
* 아이템의 정렬 순서 설정
* order:-1 /order:0 / order:1

## flex-grow  (item에 적용하는 속성)
* container 너비에서 각 아이템의 증가 비율

## flex-shrink  (item에 적용하는 속성)
* 각 아이템의 감소 비율

## flex-basis  (item에 적용하는 속성)
*  container 너비에서 각 아이템의 기본 크기

## flex  (item에 적용하는 속성)
* 증가/감소/기본의 묶음 속성
* flex:1 0 auto / 너비 grow(1) shrink(0) basis(auto)

## 1. position:relative(필수) / left , right , top , bottom(보조)**
* 자기 자신의 현재 위치를 기준으로 움직임
* relative 선택 속성 
top / bottom / left / right

## 2. position:absolute(필수) / left , right , top , bottom(보조)**
* 부모 위치를 기준으로 상대적으로 위치를 움직입니다.
* 부모 기준은 가장 가까운 부모 기준 position 값을 인식합니다.(모든 position 가능)

## 3. position:fixed(필수) / left , right , top , bottom(보조)**
* 페이지 스크롤길이와 관계없이 웹브라우저 위치에 고정됩니다.
* 팝업 요소에 주로 사용합니다.
* body를 기준으로 위치가 정해집니다.

## css-font-awesome 
* 1. font-awesome CDN link 태그로 준비한다.
* 2. awesome 전용의 font-family와 weight를 설정한다.
* 3. awesome 적용될 태그를 준비한다.
* 4. 준비한 3번 태그에 가상선택자 (after 또는 before)를 작성한다.
* 5. 가상선택자에 content속성을 입력해서 Unicode를 삽입한다.

