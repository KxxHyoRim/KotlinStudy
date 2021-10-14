# KotlinStudy

**[SOPT 29th / Android Part] Kotlin Study** <br>
**[Book] Do it! Kotlin Programming**

## Week1 (Chapter01 ~ 02)
### Ch01. 코틀린 시작하기

### 1-1 코틀린의 탄생 배경
**1. 코틀린 소개** : JVM, JS, Native 기반 실행

**2. 코틀린의 장점**
   - 자료형 오류를 미리 잡을 수 있다
   - NPE(NullPointException)에서 자유로움
   - 간결하고 효율적
   - 다중 패러다임 언어(함수형 프로그래밍과 객체 지향형 프로그래밍이 모두 가능)
   - 세미콜론 생략
**3. 안드로이드 공식 언어**(but, 하위 호완성을 고려하면 Java와 Kotlin 혼용해야함)

<br>

### 1-2 실습환경 구축하기
**1. Java JDK 설치 + 환경변수 설정**
**2. IntelliJ 설치**

<br>

### 1-3 코틀린 프로젝트 시작하기
1. p32 단축어 숙지

    <img src = 'https://user-images.githubusercontent.com/59546818/137205767-c73100e5-fb1b-48cd-9193-1fefda216707.png' width = '200'>

2. Decompile 모드를 활용하여 실행원리 파악 가능



<br/>

### Ch02. 변수와 자료형, 연산자

### 2-1 코틀린 패키지
1. 코틀린 프로젝트, 모듈, 패키지, 파일의 관계 이해하기
   - 프로젝트 > 모듈 > 패키지 > 파일
2. 보통은 모듈단위의 개발을 하나, 본 책에서는 패키지를 통해 프로그램을 관리함
3. 패키지가 상이하면 내부의 클래스 이름이 동일해도 괜찮음
4. 파일이름과 클래스 이름이 같으면 좌측 Project에 확장자가 생략됨
5. Kotlin 기본 패키지

    <img src = 'https://user-images.githubusercontent.com/59546818/137206627-14fe122c-57a6-48a2-8372-e2554f20c377.png' width = '600'/>

6. import를 통해 기본 패키지와 사용자 클래스를 참조 가능
    - ex1. import kotlin.math.PI
    - ex2. import org.sopt.edu.Person as User

<br/>

### 2-2 변수와 자료형
**1. 변수 선언과 자료형 추론**
- val : 변경 불가
- var : 변경 가능
- val username: String = "HyoRim"
- val username = "HyoRim"   // 자료형 추론가능
- val username // ❌ 값을 할당하지 않으면서 변수를 선언하려면 자료형을 반드시 지정해야함
- cf. 자료형 확인 단축키 `ctrl + Shift + p`

<br>

**2. 자료형 알아보기**
- 기본형 자료형(Primitive Data Type)
- 참조형 자료형(Reference Type) : 코틀린은 참조형
   - 컴파일러에서 기본형 대체 (최적화)
   - 기본형과 참조형의 동작 원리

      | 기본형 | 참조형|
      | ------ | -----|
      |스택에 값 저장 | 스택에 참조 주소 저장|
      | 힙 참조 안함   | 힙에 실제 객체 저장 |
1) 정수 자료형 : (부호) Long, Int[default], Short, Byte (부호X) ULong, UInt, UShort, UByte
2) 실수 자료형 : Double[default], Float  +) 부동소수점
3) 논리 자료형 : Boolean
4) 문자 자료형 : Char // 숫자 assign 불가 `65.toChar()` 활용
5) 문자열 자료형 : String
   - 저장 방식 : Stack에 주소값, Heap에 String값
   - 참조 비교를 위해 `===` 를 활용함
   - String Templete을 지원하기 때문에 `a is $a`로 출력 가능
   - 특수문자 `\` 혹은 `${''}` 안에 넣어서 출력 가능
   - 형식화된 다중 문자열은 `""" """` 사이에 넣어서 출력
   - typealias
   - 
<br/>

### 2-3 자료형 검사하고 변환하기
**1. null을 허용한 변수 검사 하기**
   - 변수에 null을 할당하려면 자료형 뒤에 물음표 붙이기 `val str1 : String? = "hello"`
   - SafeCall(?.)은 str이 null이 아니면 legth를 읽음
   - 단정기호(!!.)는 null이 아니라고 단언하는 것(NPE가 발생할 수 있음)
   - SafeCall 과 Elvis연산자 `${str1?. legth ?: -1}`
**2. 자료형 비교하고 변환하기**
   - 자료형 자동 변환 기능 없음. to자료형() 메소드 활용해야함   ex) `a.toDouble()`
   - 표현식에서 자료형이 다른 경우에는 자동 형 변환이 일어남    ex) `val result = 1L + e` // result는 Long형
   - 기본형과 참조형 자료형의 비교 원리
      - 값만 비교 (==)
      - 참조 주소 비교 (===)
      - 참조 주소 비교는 값이 동일해도 참조 주소가 다를 수 있음
   - 스마트 캐스트  ex) **Number** Class
   - 자료형 검사    ex) **is** 키워드
   - Any 자료형
   - as에 의한 스마트 캐스트 -> 묵시적 변환

<br/>

### 2-4 코틀린 연산자
1. 기본 연산자
   - 산술 연산자 : (+, -, *, /, %)
   - 대입 연산자 : (=, +=, -=, ..)
   - 증가 연산자와 감소 연산자 : (++, --) 전위 후위 구분 있음
   - 비교 연산자 : (>, <, >=, <=)
   - 논리 연산자 : (&&, ||. !)
2. 비트 연산자 : (shl, shr, ushr, and, or, inv() ...)
   - 비트 이동 연산자 shl, shr
   - 비트 이동 연산자 ushr : 부호비트까지 밀어냄, 0 채워 넣음
   - 논리곱 연산자 and
   - 배타적합 연산자 xor
   - 반전 연산자 inv -> 중위 표현법을 사용하지 않고 메소드로 활용




