# java-calculator-precourse

## 입출력 요구사항

### `input`: "1,2,3" or "1:2,3"

### `output` : "결과 : 6"

### `커스텀 구분자를 쓴 input` : “//;\n1;2;3”

### `output` : "결과 : 6"

- 커스텀 구분자는 문자열 앞부분의 “//” 와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다.
- 따라서 “//;\n1;2;3” 의 경우에는 ;이다.

## 요구사항 분석

1. 사용자는 계산기를 이용해 입력한 숫자의 합을 얻어낼 수 있다.
2. 사용자는 구분자와 양수로 구성된 `문자열`을 사용해 계산기에 입력한다.
3. 사용자는 디폴트 구분자 :와 , 를 써서 숫자를 구분할 수 있다.
4. 사용자는 커스텀 구분자도 사용할 수 있다.
5. 사용자 커스텀 구분자는 “//”, (커스텀구분자) “/n” 사이에 위치한다.
6. 사용자가 잘못된 값을 입력하면, 계산기는 종료된다.

## 예외처리

사용자가 잘못된 값을 입력할 경우, IllegalArgumentException 을 발생시키고, 애플리케이션이 종료된다.
