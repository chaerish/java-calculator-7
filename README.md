# java-calculator-precourse

### Input 과 output

`input`: 1,2,3 or 1:2,3 →  `output` : 6

`커스텀 구분자를 쓴 input` : “//;\n1;2;3”

- 커스텀 구분자는 문자열 앞부분의 “//” 와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다.
- 따라서 “//;\n1;2;3” 의 경우에는 ;이다.

## 입출력 요구사항

### **입력**

- 구분자와 양수로 구성된 문자열

### **출력**

- 덧셈 결과

```
결과 : 6
```

### **실행 결과 예시**

```
덧셈할 문자열을 입력해 주세요.
1,2:3
결과 : 6
```

### 요구사항 분석

1. 사용자는 계산기를 이용해 입력한 숫자의 합을 얻어낸다.
2. 사용자는 구분자와 양수로 구성된 `문자열`을 사용해 계산기에 입력한다.
3. 사용자는 디폴트 구분자 :와 , 를 써서 숫자를 구분할 수 있다.
4. 사용자는 커스텀 구분자도 사용할 수 있다.
5. 사용자 커스텀 구분자는 “//”, (커스텀구분자) “/n” 사이에 위치한다.
6. 사용자가 잘못된 값을 입력하면, 계산기는 종료된다.

## Exception

사용자가 잘못된 값을 입력할 경우, IllegalArgumentException 을 발생시키고, 애플리케이션이 종료된다.

### Exception의 경우

1. **사용자가 숫자가 아닌 문자열을 입력했을 때**

   Ex) “1,야,헉” → 야에서 Exception

   Ex) “hi,2,3” → 야에서 Exception

2. **사용자가 , : 같은 기본 구분자 외에 커스텀 구분자를 직접 쓸 때, “//” , “/n” 사이에 커스텀 구분자가 미리 정의되지 않은 경우**

   EX) “1?2?3?” → Exception

   EX) “@/n1@2@3” → //이 앞에 빠짐

   EX) “//@1@2@3” → /n가 빠짐

   EX) “/@/n1@2@3” → /이 하나밖에 없음

### 클래스 다이어그램: MVC 패턴

![java-calculator-6-class-diagram](..%2F..%2F%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202024-10-17%2002.11.43.png)
**CaculateResultView**

사용자에게 계산된 값을 보여주는 역할을 한다.

- 화면에 DTO를 출력한다.

**CaculateResultDTO**

- 결과 값을 DTO에 감싼다.

**CalculatorController**

- 사용자의 입력 값을 모델과 뷰에 전달한다.

### 관계

1. **CalculatorController** ───▶ **Calculator** : 연관 관계. calculator와 그 안의 함수를 사용한다.
2. **CalculatorController** - - - - - ▶ **CalculateResultDTO** : 의존 관계.
3. **CaculateResultView** - - - - - ▶ **CalculateResultDTO** :  의존 관계
