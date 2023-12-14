---
title: "Java StringBuilder란?"
description: "Java StringBuilder에 대해 알아보자"
date: 2023-07-05
update: 2023-07-05
tags:
  - Java
  - StringBuilder
series: "Java"
---

자바의 문자열은 주로 String을 사용한다. 이 문자열이 1개 이상 있을때, 붙여서 사용하는법에서 가장 간단한 방법은 StringBuilder메서드를 사용하는법이라고 생각한다. 이번엔 StringBuilder의 사용법을 알아보려고 한다.

```java
String result1 = "자바스프링 - ";
String java = "자바";
String Spring = "스프링";
String result = java + Spring;
result1 += java += Spring;
System.out.println(result);  //자바 스프링
System.out.println(result1); //자바스프링 - 자바스프링
```

> ⚠ 이런식으로 String 객체끼리 더하는 방법은 메모리 할당과 해제를 발생시키는데, 덧셈 연산이 많아진다면 성능적으로 좋지 않다.

그 이유로는 자바에서 String 객체는 변경 불가능하다. 한 번 생성되면 내용을 바꿀 수 없단 뜻이다. 따라서 하나의 문자열을 다른 문자열과 연결하면 새 문자열이 생성되고, 이전 문자열은 가비지 컬렉터로 들어간다. 문자열을 연결하는 작업은 여러 작업이 발생하고,기존 문자열 값의 길이에 추가된 문자열의 크기를 더한 크기의 새로운 문자열이 생성되는데 이런 작업을 여러번 실행하게 되면 메모리를 많이 잡아먹고,실행시간이 길어진다. 그래서 대안으로 `StringBuilder`를 많이 사용한다.  Stirng은 변경 불가능한 문자열을 생성하지만 `StringBuilder`는 변경 가능한 문자열을 만들어 준다.

```java
StringBuilder stringBuilder = new StringBuilder();
stringBuilder.append("자바").append("스프링");
        
//String str = stringBuilder;
String str = stringBuilder.toString();

// String에 StringBuilder를 그대로 넣을 순 없다. toString()을 붙여서 형변환을 해준다.
// 두 출력은 같은 값을 출력한다
System.out.println(stringBuilder); //자바스프링
System.out.println(str); //자바스프링
```
`StringBuilder의` 객체를 생성한 후, `append()`의 인자로 연결하고자 하는 문자열을 넣어서 `StringBuilder`의 객체를 통해 호출한다. 출력 시에는 `toString()`을 붙여야 하고, String변수에 넣을 때도 같다.