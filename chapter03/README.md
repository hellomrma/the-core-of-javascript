# chapter 03
- 문법  
    - 대소문자 구분  
    - 식별자  
        - 첫 번째 문자는 반드시 글자나 밑줄(_), 달러 기호($) 중 하나
        - ECMAScript의 내장 함수와 객체가 카멜 케이스로 표기되어 있음
    - 주석
        - 한 줄 주석 //
        - 블록 주석 /* ***** */
    - 스트릭트 모드
        - ECMAScript 3판의 문제를 해결했고 안전하지 않은 동작에는 에러는 반환
        - "use strict";
    - 문장
        - 문장은 세미콜론으로 종료
    - 키워드와 예약어
        - break, do typeof 등은 키워드
        - enum, int, short 등은 예약어 (스트릭트 모드에서는 일반 모드에서 left, yield 등의 예약어가 추가됨)
    - 변수
        - 