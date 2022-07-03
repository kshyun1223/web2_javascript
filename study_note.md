# 생활코딩 WEB2 - JavaScript 수업 필기노트
### JavaScript의 기본형태

```jsx
<body>
    <script>
        document.write(내용);
    </script>
</body>
```

- `<script>`: HTML 문서에 JavaScript 코드를 삽입하는 태그
- `document.write`: 문서에 텍스트를 출력하는 메소드

### 이벤트

`<input>` 태그의 타입과 속성을 지정하여 이벤트를 만들 수 있다

```jsx
<body>
    <input type="button" value="내용" onclick="alert('메시지')">
    <input type="text" onchange="alert('메시지')">              
    <input type="text" onkeydown="alert('메시지')">
</body>
```

- 버튼
    - input 태그의 타입을 button으로 지정하면 버튼이 출력 된다
    - 글자를 넣으려면 value 속성을 부여하고 원하는 내용을 값으로 입력한다
    - onclick 속성을 부여하고 값으로 `"alert('메시지')"`를 입력하면  버튼을 눌렀을 때 해당 메시지를 출력하는 경고 창이 실행된다
- 텍스트박스
    - input 태그의 타입을 text로 지정하면 텍스트를 입력할 수 있는 박스가 출력된다
    - onchange 속성을 부여하고 값으로 `"alert('메시지')"`를 입력하면  박스의 내용을 변경하고 마우스 커서를 이동하여 박스 이외의 곳을 클릭했을 때 해당 메시지를 출력하는 경고 창이 실행된다
    - onkeydown 속성을 부여하고 값으로 `"alert('메시지')"`를 입력하면  키보드를 눌렀을 때 해당 메시지를 출력하는 경고 창이 실행된다
    

### 콘솔

- 코드를 파일로 만들지 않더라도 콘솔 창에서 즉석에서 실행해 볼 수 있다

### 데이터 타입 (자료형)

- JavaScript의 데이터 타입
    - Primitives(원시값): Boolean, Null, Undefined, Number, String, Symbol
    - Object(객체)

### Number (숫자)

- 산술 연산자:  좌항의 값과 우항의 값을 결합해서 하나의 값을 만들기 때문에 이항 연산자에 속한다
    - + : 덧셈
    - － : 뺄셈
    - ＊ : 곱셈
    - ÷ : 나눗셈

### String (문자열)

- 큰 따옴표(‘ ‘) 혹은 작은 따옴표(“ “)로 이루어져 있다
- 문자열 관련 프로퍼티(Property)
    - `‘ ’.length`: 따옴표 안에 들어있는 문자의 개수를 계산
    - `‘ ’.toUpperCase()`: 따옴표 안에 들어있는 문자를 대문자로만 출력
    - `‘ ’.indexOf('문자')`: 따옴표 안에서 특정 문자 검색
    - `‘ ’.trim()`: 따옴표 안에 들어있는 문자열에서 공백을 제거
- 숫자와 문자열의 차이
    - 1+1을 입력하면 2가 출력 되지만, ‘1’+’1’을 입력하면 ‘11’이 출력 된다

### 변수(variable)와 대입 연산자

```jsx
X = 1; // 1
Y = 1; // 1
X + Y; // 2

X = 1000; // 1000
X + Y; // 1001

```

- 위 코드에서 X와 Y는 변수, =는 대입 연산자, 1과 1000은 상수(constant)라고 한다
- 동일한 내용의 엘리먼트들을 대규모로 관리해야 할 필요가 있을 경우 내용을 직접 입력하는 대신 변수를 입력하면 일괄적으로 변경할 수 있다

### 이벤트로 주간 & 야간 모드 기능을 구현

```jsx
<body>
    <input type="button" value="night" onclick="
        document.querySelector('body').style.backgroundColor = 'black';
        document.querySelector('body').style.color = 'white';
    ">
    <input type="button" value="day" onclick="
        document.querySelector('body').style.backgroundColor = 'white';
        document.querySelector('body').style.color = 'black';
    ">
</body>
```

- `document.querySelector()`: 문서 내에서 주어진 선택자를 만족하는 첫 번째 엘리먼트를 출력하는 메소드
- `style.backgroundColor`: 배경 색을 변경하는 프로퍼티
- `style.color`: 글자 색을 변경하는 프로퍼티

### 비교 연산자와 불리언

```jsx
<body>
    <script>
        document.write(값===값);
        document.write(값&lt;값);
    </script>
</body>
```

- 비교 연산자: 좌항의 값과 우항의 값을 결합해서 하나의 값을 만들기 때문에 이항 연산자에 속한다
    - `===`: 좌항과 우항의 값이 같은지 판단한다.
    - `<`: HTML에서 <는 태그를 시작하는 역할이기 때문에 < 자체를 출력하고자 할 때는 less than 이라는 뜻에서 &lt;을 입력한다
- boolean: 비교 연산자를 입력하면 true 혹은 false 중 하나의 값이 출력 되는데, 이 둘을 묶어서 불리언(boolean)이라고 한다

### 조건문

- 프로그래밍: 시간 순서에 따라 실행돼야 할 기능들을 프로그래밍 언어의 문법에 맞게 글로 적어두는 행위
- 조건문: 프로그램이 하나의 흐름으로 가는 것이 아니라 조건에 따라 다른 순서의 기능들이 실행되게 하는 것
- if-else 문
    
    ```jsx
    <body>
        <script>
        /*if - true*/
            document.write("1");
            if(true) {
                document.write("2");
            } else {
                document.write("3");
            }
            document.write("4");
    
        /*if - false*/
            document.write("1");
            if(false) {
                document.write("2");
            } else {
                document.write("3");
            }
            document.write("4");
        </script>
    </body>
    ```
    
    - true인 경우 if 뒤에 오는 코드를 출력하고, else 뒤에 오는 코드는 무시한다
    - false인 경우 else 뒤에 오는 코드를 출력하고,  if 뒤에 오는 코드는 무시한다

### night 버튼과 day 버튼을 하나로 만들기

```jsx
<body>
    <input id="night_day" type="button" value="night" onclick="
        if(document.querySelector('#night_day').value === 'night') {
            document.querySelector('body').style.backgroundColor = 'black';
            document.querySelector('body').style.color = 'white';
            document.querySelector('#night_day').value = 'day';
        } else {
            document.querySelector('body').style.backgroundColor = 'white';
            document.querySelector('body').style.color = 'black';
            document.querySelector('#night_day').value = 'night';
        }
</body>
```

- 페이지가 처음 열렸을 때는 배경이 흰색이므로 버튼은 night로 시작해야 한다
- night 버튼을 클릭했을 때 night 버튼의 value 값이 night면 night 버튼의 코드가 실행되고, 아니면 day 버튼의 코드가 실행되어야 한다
- 버튼에  id 속성을 부여하고 용도에 맞게 night_day와 같이 이름 붙인다
- 다시 주간 모드를 실행시키기 위해 야간 모드에서는 버튼의 value 값이 day가 되어야 한다
    - 콘솔에 `document.querySelector('#엘리먼트_이름').value`를입력하면 해당 엘리먼트의 value 값이 출력된다

### 리팩터링

- 리팩터링: 동작사항은 변경하지 않고 코드 자체의 가독성을 높이며, 유지 보수를 편리하게 만들고, 중복된 코드를 줄이는 방향으로 개선하는 작업
    
```jsx
<body>
    <input type="button" value="night" onclick="
        var target = document.querySelector('body');
        if(this.value === 'night') {
            target.style.backgroundColor = 'black';
            target.style.color = 'white';
            this.value = 'day';
        } else {
            target.style.backgroundColor = 'white';
            target.style.color = 'black';
            this.value = 'night';
        }
    ">
</body>
```
    
    - 일일이 id 값을 부여하는 대신 자기 자신을 가리키는 this 키워드를 사용한다
    - 반복적으로 등장하는 querySelector 메소드를 target 변수로 대체한다. 이를 위해 body 태그를 target 변수에 할당하고 여기에 querySelector 메소드를 적용한다.

### 배열

```jsx
<body>
    <script>
    /*배열 생성*/
        var 배열a = ["항목a", "항목b"];

    /*항목 출력*/
        document.write(배열a[0]);
        document.write(배열a[1]);

    /*항목 수 출력*/
        document.write(배열a.length);

    /*항목 추가*/
        배열a.push('항목c')
        배열a.push('항목d')
    </script>
</body>
```

- 배열(Array): 서로 연관된 데이터를 정리해서 담아두는 일종의 수납 상자라고 할 수 있다
    - 대괄호로 시작해서 대괄호로 끝나며, 값과 값 사이는 콤마( , )로 구분한다
    - 순서는 인덱스(index)라 하여 0부터 시작한다
    - 배열에 `.length` 프로퍼티를 지정하면 배열 안에 있는 항목의 개수를 출력한다
    - 배열에 데이터를 추가하려면 `.push` 메소드를 사용
    

### 반복문

```jsx
<body>
    <ul>
        <script>
            document.write('<li>1</li>');
            var i = 0;
            while(i<3) {
                document.write('<li>2</li>'); 
                document.write('<li>3</li>'); 
                i = i + 1;
            }    
            document.write('<li>4</li>');
        </script>
  </ul>
</body>
```

- 조건이 true이면 while문이 계속 반복해서 실행된다
- 조건이 false가 되면 while문 이후의 코드가 실행된다
- 변수 i는 반복횟수를 의미한다
    - `var i=0`은 i의 초기값이 0이라는 뜻
    - `i=i+1`은 반복문이 실행될 때마다 i의 값을 1씩 증가시킨다
    - `while(i<3)`이므로 i의 값이 0, 1, 2일 때 반복문이 실행되며, i의 값이 3이 되면 반복문이 종료되고 다음 코드가 실행된다

### 배열과 반복문의 결합

```jsx
<body>
    <script>
        var 배열a = ['항목a', '항목b', '항목c', '항목d'];
    </script>
    <ul>
        <script>
            var i = 0;
            while(i < 배열a.length) {
                document.write('<li>' + 배열a[i] + '</li>');
                i=i + 1;
            }
        </script>
    </ul>
</body>
```

- 반복문에 의해 배열에 담긴 데이터가 자동적으로 목록으로 작성된다
- 반복 횟수를 특정한 값이 아닌 배열의 항목 수(`배열명.length`)로 설정하면 배열의 구성이 변경되어도 자동적으로 대응하여 반복문이 실행된다

### 주간 & 야간 모드 기능에 배열과 반복문 적용

```jsx
<body>
    var alist = document.querySelectorAll('a');
    var i = 0;
    while(i < alist.length) {
        alist[i].style.color = '색상';
        i = i + 1;
    }
</body>
```

- `<a>` 태그를 alist 변수에 할당하고 여기에 querySelectorAll을 적용한다
    - `document.querySelectorAll()`: 문서 내에서 주어진 선택자를 만족하는 모든 엘리먼트를 출력하는 메소드
- 위 코드를 주간 모드와 야간 모드의 아래에 각각 추가하고 필요한 색상을 지정한다

### 함수

- 연속되지 않게 반복되는 코드를 작성하는 경우 반복문을 사용할 수 없는데, 이때 함수를 사용하여 구현할 수 있다.
    
    ```jsx
    <body>
        <script>
            function 함수명() {
                document.write('<li>2-1</li>');
                document.write('<li>2-2</li>');
            }
            document.write('<li>1</li>');
            함수명(); // 2-1
            document.write('<li>3</li>');
            함수명(); // 2-2
        </script>
    </body>
    ```
    

### 매개변수와 인자

- 1+1을 함수로 구현
    
    ```jsx
    <body>
        <script>
            function 함수명() {
                document.write(1+1);
            }
            함수명(); // 2
        </script>
    </body>
    ```
    
- 입력값에 따라 다른 결과를 출력하는 함수
    
    ```jsx
    <body> 
        <script>
            function 함수명(left, right) {
                document.write(left + right);
            }
            함수명(2,3); // 5
            함수명(3,4); // 7
        </script>
    </body>
    ```
    
    - 위 코드에서 2, 3, 4와 같이 함수로 전달되는 값을 인자(argument)라고 한다.
    - left, right와 같이 값을 받아서 함수로 매개하는 변수를 매개변수(parameter)라고 한다.

### return

```jsx
<body>
    <script>
        function 함수명(left, right) {
            return left + right;
        }
        document.write(함수명(2,3) + '<br>');
        document.write('<div style="color: 색상">' + 함수명(2,3) + '</div><br>');
        document.write('<div style="font-size: 값">' + 함수명(2,3) + '</div><br>');
    </script>
</body>
```

- 함수를 document 메소드가 아닌 return으로 출력하면 함수를 바로 실행하지 않고 결괏값만을 돌려준다. 이를 통해 함수의 결괏값에 다양한 속성을 적용할 수 있다.

### night & day 버튼을 함수로 구현

```jsx
<head>
    <script>
        function LinksSetColor(color) {
            var alist = document.querySelectorAll('a');
            var i = 0;
            while(i < alist.length) {
                alist[i].style.color = color;
                i = i + 1;
            }
        }

        function BodySetColor(color) {
            document.querySelector('body').style.color = color;
        }

        function BodySetBackgroundColor(color) {
            document.querySelector('body').style.backgroundColor = color;
        }

        function nightDayHandler(self) {
            var target = document.querySelector('body');
            if(self.value === 'night') {
                BodySetBackgroundColor('black');
                BodySetColor('white');
                self.value = 'day';

                LinksSetColor('powderblue');
            } else {
                BodySetBackgroundColor('white');
                BodySetColor('black');
                self.value = 'night';

                LinksSetColor('blue');
            }
        }
    </script>
</head>
<body>
    <input type="button" value="night" onclick="
        nightDayHandler(this);
    ">
</body>
```

- nightDayHandler 함수를 만들고 input 버튼의 코드를 옮겨 넣는다
- nightDayHandler 함수를 input 버튼의 onclick 속성값으로 지정
- 버튼의 인자 this를 함수에서 매개변수 self로 받는다
    - 함수에서 this를 self로 변경: 인자 this는 코드가 태그의 속성으로 있을 때 해당 태그를 가리키는 것이기 때문에 독립된 함수에서는 작동하지 않는다.
- 코드의 의미를 명료하게 하기 위해 각각의 기능들을 별개의 함수로 만들어 구분한다.
    - 함수명이 중복될 경우 먼저 실행된 코드가 나중에 실행된 코드에 의해 덮어쓰여져 중단되기 때문에 함수명은 최대한 세부적이고 구체적으로 지정해야 한다.

### 객체

```jsx
<body>
    <script>
        var 객체명 = {
            "키1":"값1",
            "키2":"값2"
        }
        document.write(객체명.키1 + "<br>");
        document.write(객체명.키2 + "<br>");
        객체명.키3 = "값3";
        document.write(객체명.키3 + "<br>");
        coworkers["키4 공백"] = "값4";
        document.write(객체명["키4 공백"] + "<br>");
    </script>
</body>
```

- 객체에 포함된 각각의 내용을 프로퍼티(property)라고 한다
    - 프로퍼티는 이름(key)과 값(value)으로 이루어져 있다.
- `document.write(객체명.이름)` : 프로퍼티의 값을 출력
    - 객체명과 키 사이에 있는 온점( . )은 객체에 접근하는 연산자라는 뜻에서 객체 접근 연산자(object access operator)라고 부른다
- `객체명.이름 = "값"` : 객체에 프로퍼티를 추가
- 프로퍼티 이름에 공백이 있으면 대괄호로 감싸야 한다
    - `객체명.["공백 이름"] = "값"` : 이름에 공백이 포함된 프로퍼티를 추가
    - `document.write(객체명["공백 이름"])` : 이름에 공백이 포함된 프로퍼티의 값을 출력

### 객체와 반복문의 결합

```jsx
<body>
    <script>
        for(var key in 객체명) {
            document.write(key + ' : ' + 객체명[key] + '<br>'); // key : 값
        }
    </script>
</body>
```

- 반복문을 객체에 적용하면 모든 프로퍼티를 한 번에 출력할 수 있다.
- 위 코드에서 `key`는 프로퍼티의 이름(key), `객체명[key]`는 프로퍼티의 값(value)에 해당한다.

### 객체 프로퍼티와 메소드

```jsx
<body>
    <script>
        객체명.메소드명 = function() {
            for(var key in this) {
                document.write(key + ' : ' + this[key] + '<br>');
            }
        }

        객체명.메소드();
    </script>
</body>
```

- 객체에는 함수도 담을 수 있다. 객체에 들어있는 함수는 메소드라고 하며, 변수는 프로퍼티라고 한다.
- `객체명.메소드명 = function(){}` : 객체에 메소드를 추가하는 코드. 이는 함수에서의 `function 함수명(){}`과 같다.
- 메소드에 반복문을 추가한다
    - 객체의 이름이 바뀌면 함수가 데이터를 가져오지 못해서 실행되지 않는다
    - 객체명 대신  this 키워드를 사용하면 이를 방지할 수 있다
    - 여기서 this는 함수가 속해있는 객체를 가리킨다.
- `객체명.메소드()` : 메소드를 실행하는 코드.

### 주간 & 야간 모드 기능에 객체 적용

```jsx
<head>
    <script>
        var Body = {
            setColor: function(color) {
                document.querySelector('body').style.color = color;
            },
            setBackgroundColor: function(color) {
                document.querySelector('body').style.backgroundColor = color;
            }
        }

        var Links = {
            setColor: function(color) {
                var alist = document.querySelectorAll('a');
                var i = 0;
                while(i < alist.length) {
                    alist[i].style.color = color;
                    i = i + 1;
                }
            }
        }

        function nightDayHandler(self) {
            var target = document.querySelector('body');
            if(self.value === 'night') {
                Body.setBackgroundColor('black');
                Body.setColor('white');
                self.value = 'day';
            
                Links.setColor('powderblue');
            } else {
                Body.setBackgroundColor('white');
                Body.setColor('black');
                self.value = 'night';

                Links.setColor('blue');
            }
        }
    </script>
</head>
```

- 함수들을 객체 메소드로 변경한다.
- 변수를 생성하고 그 안에 객체를 담는다: `var Body`, `var Links`
- 객체에 프로퍼티를 추가한다.
    - 객체에서는 프로퍼티와 프로퍼티의 사이에 콤마( , )를 입력하여 구분한다

### JavaScript 코드의 재사용

- `color.js` 파일을 생성하고 공통 코드를 붙여넣는다
- 각 파일의 공통 코드를 지우고, 그 대신에 `color.js` 파일을 추가한다
    - `<script src="color.js"></script>`

### 라이브러리와 프레임워크

- 라이브러리와 프레임워크의 차이
    - 라이브러리: 완제품
    - 프레임워크: 반제품
- 라이브러리 추가 방법
    - 직접 파일을 다운받아서 프로젝트에 추가
    - CDN을 사용
- CDN(Content Delivery Network): 코드에 src 속성을 삽입하여 서비스 업체의 서버에 업로드되어 있는 라이브러리를 불러오는 방식.
- Google CDN으로  jQeury 라이브러리 불러와서 사용하기
    
    ```jsx
    <head>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    </head>
    ```
    
- jQeury를 이용해 `color.js` 파일 수정
    
    ```jsx
    var Links = {
        setColor: function(color) {
            $('a').css('color', color);
        }
    }
    var Body = {
        setColor: function(color) {
            $('body').css('color', color);
        },
        setBackgroundColor: function(color) {
            $('body').css('backgroundcolor', color);
        }
    }
    ```
    
- 주석: 원하는 부분을 드래그하고 Ctrl+/ 를 누르면 주석 처리 된다
- `$('선택자')`는 페이지 상에 있는 존재하는 모든 해당 태그를 jQuery로 제어한다는 뜻이다

### UI vs. API

- UI(User Interface): 사용자가 시스템을 제어하기 위해 사용하는 조작장치
- API(Application Programming Interface): 개발자가 애플리케이션을 개발할 때 사용하는 조작장치
    - 모든 애플리케이션은 API를 프로그래밍적으로, 즉 순서대로 실행하는 방식으로 만들어진다

### 웹 브라우저에 탑재되어 있는 API 예시

- document 객체: 어떤 웹 페이지의 태그를 삭제하고 싶거나 어떤 태그의 자식 태그를 추가하고 싶은 경우
- DOM 객체: document 객체의 상위분류이다
- window 객체: 웹 페이지가 아니라 웹 브라우저 자체를 제어해야 하는 경우
- Ajax: 웹 페이지를 리로드하지 않고도 정보를 변경하고 싶은 경우
- cookie: 웹 페이지가 리로드돼도 현재 상태를 유지하고 싶은 경우