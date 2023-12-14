---
title: "Java 정수형의 오버플로우와 언더플로우"
date: 2023-06-25
update: 2023-06-25
tags:
  - Java
  - 오버플로우
  - 언더플로우
series: "Java"
---

코드를 작성 후 실행 중일때, 타입의 정해진 범위를 넘는 경우가 발생할 수 있다.

예를 들어 byte타입의 경우 127까지 표현 가능하지만, byte타입이 127을 넘을 결우 오버플로우가 발생한다.

반대의 경우 byte타입이 -128보다 값이 적을경우에 최소값을 넘기 때문에 언더플로우가 발생한다.

```java
//정수 오버플로우, 언더플로우의 예시
public static void main(String[] args) {

    byte Of = 125;
    byte Uf = -125;

    byte result = (byte) (Of + 10);
    byte result2 = (byte) (Uf - 10);

    System.out.println(result); // 오버플로우 발생 : -121
    System.out.println(result2); // 언더플로우 발생 : 121

}
```

컴파일 에러가 발생하지 않았지만, 제대로된 값을 얻지 못했다. 그 이유는 byte형의 범위를 넘었기 때문이다. 올바른 값을 얻기위에서는 byte타입이 아닌 int타입이어야 한다.

> 정수형의 오버플로우와 언더플로우는 컴파일러가 오버플로우, 언더플로우를 무시해서  잘못된 값이 저장되기 때문에 발생한경우 알아보기 힘들어서 매우 위험하다. 정해진 연산을 처리하면서 잘못된 결과로 프로그램의 오작동을 발생할수 있고, 보안에 취약한 부분을 내포하게 된다.

### 오버플로우와 언더플로우를 피하는 안전한 코딩법

- 언어 ・ 플랫폼별 정수 타입의 범위를 확인하여 사용
- 정수형 변수를 연산에 사용하는 경우 결과 값의 범위를 체크하는 모듈을 사용
- 외부입력값을 동적 메모리 할당에 사용하는 경우, 변수값이 적절한 범위 내에 존재하는지 값인지 확인

### 타입별 범위 확인
각 타입별 허용 범위는 각 타입별 클래스의 MIN_VALUE(최소값), MAX_VALUE(최대값) 메소드를 통해 타입의 범위를 확인할 수 있다.
```java
System.out println"char: " + (int)Character.MIN_VALUE + " ~ " + (int) Character. MAX_VALUE) ;

System.out.println("byte: " + Byte.MIN_VALUE + " ~ " + (int)Byte.MAX_VALUE) ;

System.out.println("short:" + Short. MIN_VALUE + " ~ " + Short. MAX_VALUE) ;

System.out.println("int: " + Integer MIN_VALUE + " ~ " + Integer.MAX_VALUE) ;

System.out.println("long: " + Long.MIN_VALUE + " ~ " + Long.MAX_VALUE) ;

System.out.println("float: " + Float. MIN_VALUE + " ~ " + Float.MAX_VALUE) ;

System. out. println("double:" + Double. MIN_VALUE + " ~ " + Double. MAX_VALUE) ;
```

### 결과
```
char: 0 ~ 65535
byte: -128 ~ 127
short: -32768 ~ 32767
int: -2147483648 ~ 2147483647
Long: 9223372036854775808 ~ 9223372036854775807
float: 1.4-45 ~ 3.4028235E38
double: 4.9E-324 ~ 1.7976931348623157E308
```