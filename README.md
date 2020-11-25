# learn-vue-js
:2020-11-25

# vscode plug-in
- Vetur
- Night Owl
- Material Icon Theme
- Live Server
- ESLint
- Prettier
- Auto Close Tag
- Atom Keymapss

# 단축키 
- 크롬 개발자도구(mac) 단축키 command + option + i 
- 패널 접기 command + w 

# 자료 참고 
- MDN 페이지 

# Vue는 무엇인가?
- MVVM(Model + View + ViewModel) 패턴의 뷰모델(ViewModel) 레이어에 해당하는 화면(View)단 라이브러리 
- DOM이 view 역할, 자바스크립트가 Model역할 
- 뷰모델이 없으면 getElementById와 같이 DOM을 직접 다뤄서 모델과 뷰를 연결해야한다. 그렇게 되면 코드양이 증가하는데, 그것을 뷰모델이 대신 수행해 주는 것이 MVVM 모델이다 

# web-dev
- 웹페이지를 단순 구성하려면 html, css, javascript를 사용 
- 선언하고 값을 바꾸면, html 값을 바꿔주는 작업이 다시 필요함 
```
var str = 'hello world';
div.innerHTML = str;

str = 'hello world!!!';
div.innerHTML = str;
```

# web-dev(reacitivity)
- 데이터 바인딩. 뷰의 핵심  
- `데이터의 변화를 라이브러리에서 감지해서 알아서 화면을 자동으로 그려줌`  
- 리액티비티를 즉시 실행 함수 표현으로 라이브러리화 할 수 있다 
  + ```
    (function () {
        statements
    })();
    ```
  + https://developer.mozilla.org/ko/docs/Glossary/IIFE

# instance 뷰 인스턴스 
- 생성 
  + new Vue();
  + ```
    var vm = neww Vue();
    consoloe.log(vm);
    ```
- Vue 인스턴스는 다양한 기능(API)과 속성을 제공한다 
- 생성자 함수를 이용해 Vue 인스턴스에 함수를 새로 정의하면 재사용성이 높아진다 
  + 생성자 함수 만들고 인스턴스 생성
    ```
    function Person(name, job) {
    this.name = name;
    this.job = job;
    }

    var p = new Person('josh', 'developer');
    ```
    ```
    function Vue() {
    this.logText = function() {
        console.log('hello');
        }
    }
    
    var vm = new Vue();
    vm.logText;
    ```
- 인스턴스에서 사용할 수 있는 속성과 API들 
  + ```
    new Vue({
        el: , 인스턴스가 그려지는 화면의 시작점. 특정 HTML 태그
        template: , 화면에 표시할 요소. HTML, CSS 등 
        data: , 뷰의 반응성(Reactivity)가 반영된 데이터 속성 
        methods: , 화면의 동작과 이벤트 로직을 제어하는 메서드 
        created: , 뷰의 라이프 사이클과 관련된 속성 
        watch: , data에서 정의한 속성이 변화했을 때 추가 동작을 수행할 수 있게 정의하는 속성
    });
    ```
