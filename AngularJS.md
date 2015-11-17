#Angular.js
- javascript MV* framework (Angular.js, Backbone.js, Ember.js, CanJS, Maria) 중 하나

#Angular JS를 선택해야하는 이유
##1. 작성해야하는 자바스크립트 코드량을 줄일 수 있다
- Jquery를 이용한 것보다 절반 이상 코드량을 줄일 수 있다
- Angular.js에서 MVC구조를 제공하므로 별도로 MVC구조를 위한 코드를 작성하지 않아도 된다
- 화면의데이터와 모델의데이터 사이에 양방향 데이터 바인딩을 제공하므로 뷰데이터와 모델데이터를 서로동기화하는 코드작성할 필요 없다

##2. Angular.js의 데이터 모델은 단순 자바스크립트객체이다.
- POJO (spring과 유사)

##3. 재사용할 수 있는 UI컴포넌트를 만들 수 있다
- html의 form태그와 같이 재사용가능한 UI컴포넌트들
```javascript
- <map>, <graph>, <table sortale="true">
```

##4. 의존관계주입을 이용해 웹 애플리케이션 자바스크립트 개발을 할 수 있다
- DI(Dependency Injection) -> 어려운개념! 공부해보쟈ㅎㅎ

##5. Angular.js는 HTML을 이용해 뷰코드를 작성하고, 자바스크립트에서 비즈니스 로직 코드만을 작성하게 해 뷰코드와 로직코드를 명확히 분리했다
- 즉, 자바스크립트가 HTML의 구조를 알 필요가 없다

##Angular.js 가 제공하는 주요기능
- 양방향 데이터 바인딩
- MVC구조
- 지시자(directive)를 이용한 HTML확장
- 의존관계 주입(dependency injection)
- 단일 페이지 웹 애플리케이션을 위한 라우터(router)
- $q를 이용한 자바스크립트 비동기 프로그래밍 지원
- 자바스크립트 테스팅 지원

##지시자 (dierctive)
- ng-app이나 ng-init같은 별도의 HTML태그나 속성
- HTML에서 표준으로 제공하지 않고 AngularJS가 제공하는 속성 또는 태그
- 이런 지시자를 사용하면 동적이고 화려한 웹애플리케이션을 만들 수 있다
- ng-app 지시자를 사용해 해당 HTML펭지가  AngularJS기반의 웹 애플리케이션이라고 선언한다
- ng-init속성에 "appName = 'AngularJS TODO APP'"이라는 표현식을 작성함으로써, appName이라는 변수에 'AngularJS TODO APP'이라는 문자열을 대입
- AngularJS가 전체 HTML코드를 읽어 {{ appName }}부분을 해석하여 appName변수의 값으로 치환한다

##데이터 바인딩과 MVC패턴
- 제이쿼리 소스는 아래와같음
```javascript
<h1 id="appName"></h1>
//로그인했을 때 처리
$("#appName").text("서자랑의 TODO APP");
```
- 실질적인 로직보다 DOM처리에 더 많은 시간을 빼앗기게됨
- AngularJS는 appName과 같은 모델(M)이 바뀌면 뷰(V)를 자동으로 개인해 모델의 상태와 뷰의 상태를 일치시켜준다
- 모델(M)의 값은 컨트롤러(C)에서 변경할 수 있다

##07 지시자의 모든 것
- AngularJS는 해당 DOM과 연결된 하나의 함수를 만들고 이 함수가 DOM을 조작하여 새로운 기능 추가하는 행위를 할 수 있다
- 지시자 함수는 연결된 특정 DOM에 $scope를 연결하거나 연결된 DOM을 조작하여 특정행위를 할 수 있다
- 지시자의 이름은 낙타표기법(camel case)로 작성
- 이런 지시자의 이름을 HTML 즉, 템플릿에서는 대문자로 시작되는 부분에 :, -, _를 넣고 대문자를 소문자로 바꾸어 사용할 수 있다
- ex) myDirective => my-directive, my:directive, my_directive

#EACM 문자 조합으로 문자열을 줄 수 있다
##1. 요소의 속성을 이용한 호출 - A
```javascript
<span my-directive="expression"></span>
```
##2. 요소의 클래스를 이용한 호출 - C
```javascript
<span class="my-directive: expression;"></span>
```
##3. 요소의 이름을 이용한 호출 - E
```javascript
<my-directive></my-directive>
```
##4. 코멘트를 이용한 호출 - M
```javascript
<!-- directive: my-directive expression-->
```
