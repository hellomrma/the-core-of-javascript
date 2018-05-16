# 기초

- 문법  
    - 대소문자 구분  
    - 식별자  
        - 첫 번째 문자는 반드시 글자나 밑줄(_), 달러 기호($) 중 하나
        - ECMAScript의 내장 함수와 객체가 카멜 케이스로 표기되어 있음. 그러므로 카멜 케이스로 쓰는걸 권장
    - 주석
        - 한 줄 주석 //
        - 블록 주석 /* ***** */
    - 스트릭트 모드
        - ECMAScript 3판의 문제를 해결했고 안전하지 않은 동작에는 에러는 반환함
        - "use strict";
    - 문장
        - 문장은 세미콜론으로 종료
---
- 키워드와 예약어
    - break, do, typeof 등은 키워드
    - enum, int, short 등은 예약어 (스트릭트 모드에서는 일반 모드에서 left, yield 등의 예약어가 추가됨)
---
- 변수
    - ECMAScript는 느슨한 변수 타입 사용 (어떤 타입의 데이터라도 가능)
    - var 연산자는 변수를 로컬 스코프에서 정의
    - var 연산자를 생략하면 변수를 전역으로 정의할 수 있음
---
- 데이터 타입
    - ECMAScript에는 다섯 가지 기본적인 데이터 타입이 있음 (원시 데이터 타입)
    - Undefined, Null, 불리언(Boolean), 숫자, 문자열 + 객체
    - typeof 연산자
        - 데이터 타입을 확인 할 수 있음  
    - undefined 타입
        - 초기화 하지 않은 변수에는 항상 undefined 값이 할당됨
    - Null 타입
        - null에 typeof를 호출하면 object를 반환함
        - 변수가 객체를 가리키게 할 생각이라면 해당 변수에는 null로 초기화하길 권장함
    - 불리언 타입
        - true와 false 두 가지 리터럴 값만 가짐
    - 숫자 타입
        - 정수와 부동소수점 숫자
        - 부동소수점 숫자
            - 부동소수점 숫자를 저장할 때는 메모리를 두 배로 소모함. 그래서 ECMAScript에서는 가능한 한 정수로 변환하여 저장하려 함.
            - 전체 숫자 표기법 - 1.0, 100.00
            - e-표기법(지수 표기법) - 3.125e7
        - 숫자 범위
            - 자바스크립트의 숫자형 범위에서 나타낼 수 없는 숫자라면 Infinity로 변환됨
        - NaN (Not a Number)
            - isNaN() : 숫자가 아닌 값인지 검사하기 위함
        - 숫자 변환
            - 숫자가 아닌 갑을 숫자로 바꾸는 함수 Number(), parseInt(), parseFloat()
            - parseInt("10", 10) 두번째 매개변수는 진수를 표현함
    - 문자열 타입
        - 문자열 데이터 타입은 16비트 유니코드 문자의 연속
        - 큰따옴표나 작은따옴표 둘다 사용가능
        - 문자 리터럴
            - \n 줄바꿈 \t 탭 \b 백스페이스 \r 캐리지 리턴
        - 문자열의 성질
            - ECMAScript에서 문자열은 불변 (문자열을 바꾸려면 기존의 문자열을 파괴하고 새 문자열을 채워야 함)
        - 문자열로 변환
            - 값을 문자열로 바꾸는 방법은 두가지
            - toString()
            - toString(매개변수) - 진법을 나타낼 수 있음. 기본 10진법
    - 객체 타입  
    객체는 new 연산자 다음에 새로 만들 객체 타입의 이름을 써서 만듬  
    ```javascript
    var o = new Object();
    ```
    - ECMAScript에서는 생성자에 매개변수를 넘기지 않는다면 괄호를 생략해도 됨  
    ```javascript
    var o = new Object;
    ```
    - Object의 인스턴스는 다음 프로퍼티와 메서드를 가짐
        - constructor  
        : 해당 객체를 만드는 데 쓰인 함수
        - hasOwnProperty(propertyName)  
        : 해당 프로퍼티가 객제 인스턴스에 고유하며 프로토타입에서 상속하지 않았음을 확인
---
- 연산자  
    - 계산 연산자, 비트 연산자, 관계 연산자, 일치 연산자 등
    - 단항 연산자
        - 증감 연산자 (++number, --number, number++, number--)
        - 단항 플러스와 단항 마이너스 (+number, -number)
    - 비트 연산자
        - 비트 NOT, 비트 AND, 비트 OR, 비트 XOR
    - 불리언 연산자
        - 논리 NOT : 느낌표(!) 
        - 논리 AND : 앰퍼센드 2개(&&)
        - 논리 OR : 파이프 2개(||)  
        ```javascript
        var myObject = preferredObject || backupObject;
        ```
    - 곱셈 관련 연산자
        - 곱셈 : 아스테리스크(*)
        - 나눗셈 : 슬래시(/)
        - 나머지 : 퍼센트 기호(%)
    - 덧셈 관련 연산자
        - 덧셈 : +
        - 뺄셈 : -
    - 관계 연산자
        - 미만(<), 초과(>), 이하(<=>), 이상(>=)
    - 동일 연산자
        - 사용 : ==
        - 두 피연산자가 동일하면 true를 반환
        - 문자열의 경우 숫자로 변환
        - null == undefined는 true
    - 비동일 연산자
        - 사용 : !=
        - 두 피연산자가 동일하지 않으면 true를 반환
        - 문자열의 경우 숫자로 변환
    - 일치 연산자
        - 사용 : ===
        - 피연산자의 타입을 변환하지 않고 있는 그대로 비교
        - null === undefined는 false
    - 불일치 연산자
        - 사용 : !==
        - 피연산자의 타입을 변환하지 않고 있는 그대로 비교
    - 3항 연산자  
    ```javascript  
    variable = boolean_expression ? true_value : false_value
    ```
    - 할당 연산자  
    값을 변수에 할당
    ```javascript
    var num = 10;
    num = num + 10;
    ```
    - 곱셈 후 할당 (*=), 나눗셈 후 할당 (/=), 나머지 할당 (%=), 덧셈 후 할당 (+=), 뺄셈 후 할당 (-=)
    - 쉼표 연산자  
    여러 문장을 한 문장으로 합칠 때 씀
    ```javascript
    var num1=1, num2=2, num3=3
    ```
    - 아래와 같이 쓰면 표현식의 마지막 값을 반환 (아래 예제에서는 0을 반환)
    ```javascript
    var num = (5,1,4,8,0)
    ```
---
- 문장
    - if 문  
    condition의 결과에 Boolean() 함수를 호출해 불리언 값으로 바꿈
    ```javascript
    if (condition) {
        statement1
    } else if (condition2) {
        statement2
    } else {
        statement3
    }
    ```
    ```javascript
    if (i > 25) {
        alert("Greater than 25");
    } else if (i < 0) {
        alert("Less than 0");
    } else {
        alert("Between 0 and 25, inclusive");
    }
    ```
    - do-while 문  
    평가전 루프 (종료 조건을 평가하기 전에 최소 한 번은 반드시 실행)
    ```javascript
    do {
        statement
    } while (expression);
    ```
    ```javascript
    var i=0;
    do {
        i+=2;
    } while (i < 10);
    ``` 
    - while 문  
    평가후 루프 (루프 본문을 실행하기 전에 종료 조건을 평가함)
    ```javascript
    while(expression) statement
    ```
    ```javascript
    while (i < 10) {
        i+=2;
    }
    ```
    - for 문  
    평가후 루프 (루프 본문을 실행하기 전에 종료 조건을 평가함)
    ```javascript
    for (initialization; expression; post-loop-expression) statement
    ```
    ```javascript
    var count = 10;
    for (var i = 0; i < count; i++) {
        alert(i);
    }
    ```
    - for-in 문  
    엄격한 반복문. 객체의 프로퍼티를 나열하는 데 사용함
    ```javascript
    for (property inexpression) statement
    ```
    ```javascript
    for (var propName in window) {
        document.write(propName);
    }
    ```
    - 문장 레이블  
    문장에 레이블을 붙였다가 나중에 사용할 수 있음  
    나중에 break나 continue 문에서 참조할 수 있음  
    중첩된 루프에서 사용함
    ```javascript
    label: statement
    ```
    ```javascript
    start: for (var i = 0; i < count; i++) {
        alert(i);
    }
    ```
    - break 문과 continue 문  
    루프 내부의 코드 실행을 세밀히 조절할 수 있음  
    break 문은 즉시 루프에서 빠져나감  
    continue 문은 루프를 즉시 빠져나가긴 하지만 루프 실행을 계속 됨  
    ```javascript
    var num=0;
    for (var i = 1; i < 10; i++) {
        if (i % 5 == 0) {
            break;
        }
        num++
    }
    alert(num); // 8
    ```
    ```javascript
    var num=0;
    for (var i = 1; i < 10; i++) {
        if (i % 5 == 0) {
            continue;
        }
        num++
    }
    alert(num); // 55
    ```
    - with 문  
    코드의 스코프(실행 범위)를 특정 객체에 고정함  
    스트릭트 모드에서는 with 문을 금지하고 문법 에러로 간주함  
    우선 지역 변수에서 식별자로 찾고 없다면 location 객체의 프로퍼티 중에서 같은 이름으로 검색  
    with 문은 성능에 악영향이 있고 디버깅하기도 어려우므로 쓰지 않는게 좋음
    ```javascript
    with (expression) statement;
    ```
    ```javascript
    var qs = location.search.substring(1);
    var hostName = location.hostname;
    var url = location.href;
    ```
    ```javascript
    with(location) {
        var qs = search.substring(1);
        var hostName = hostname;
        var url = href;
    }
    ```
    - switch 문  
    if 문과 관련이 깊음  
    switch 문의 각 case는 '표현식이 value와 일치하면 statement를 실행하라'는 의미  
    모든 데이터 타입에서 동작하므로 문자열과 객체에서도 사용할 수 있음  
    일치 연산자(===)로 값을 비교하므로 타입 변환은 일어나지 않음. 문자와 숫자를 서로 다른 것으로 간주
    ```javascript
    switch (expression) {
        case value: statement
            break;
        case value: statement
            break;
        default: statement
    }
    ```
    ```javascript
    switch (i) {
        case 25:
            alert("25");
            break;
        case 35:
            alert("35");
            break;
        default:
            alert("Other");
    }
    ```