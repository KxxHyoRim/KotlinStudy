# KotlinStudy

**[SOPT 29th / Android Part] Kotlin Study** <br>
**[Book] Do it! Kotlin Programming**

## Week1 (Chapter01 ~ 02)
### Ch01. 코틀린 시작하기

#### 1-1 코틀린의 탄생 배경
1) 코틀린 소개 : JVM, JS, Native 기반 실행
2) 코틀린의 장점
   - 자료형 오류를 미리 잡을 수 있다
   - NPE(NullPointException)에서 자유로움
   - 간결하고 효율적
   - 다중 패러다임 언어(함수형 프로그래밍과 객체 지향형 프로그래밍이 모두 가능)
   - 세미콜론 생략
3) 안드로이드 공식 언어(but, 하위 호완성을 고려하면 Java와 Kotlin 혼용해야함)

#### 1-2 실습환경 구축하기
1. Java JDK 설치 + 환경변수 설정
2. IntelliJ 설치

#### 1-3 코틀린 프로젝트 시작하기
1. p32 단축어 숙지

    <img src = 'https://user-images.githubusercontent.com/59546818/137205767-c73100e5-fb1b-48cd-9193-1fefda216707.png' width = '200'>

2. Decompile 모드를 활용하여 실행원리 파악 가능



<br/>

### Ch02. 변수와 자료형, 연산자

#### 2-1 코틀린 패키지
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

#### 2-2 변수와 자료형
#### 2-3 자료형 검사하고 변환하기
#### 2-4 코틀린 연산자
