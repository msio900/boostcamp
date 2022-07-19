# 객체지향언어의 이해

만들어 놓은 코드를 **재사용** 하고 싶다!

`클래스`와 `객체` : 객체 지향 언어의 이해

### 수강신청 프로그램을 만들고 싶다면?

1. 수강신청이 시작부터 끝까지 순서대로 작성!

2. 수강신청 관련 **주체들**(교수, 학생, 관리자)의 **행동**(수강신청, 과목 입력)과 **데이터**(수강과목, 강의 과목)들을 중심으로 프로그램 작성 후 연결

### 두 가지 모두 가능하지만, 최근엔 **2번 방법**이 주류를 이룸. 

### -> 이러한 기법을 객체 지향 프로그램이라 함.

## 객체지향 프로그래밍 개요

- Object-Oriented Programming, **OOP**

- 객체 : 실생활에서 일종의 물건 - **속성**(Attribute)과 **행동**(Action)을 가짐

- OOP는 이러한 객체 개념을 프로그램으로 표현 - **속성은 변수(Variable)**, **행동은 함수(Method)**로 표현됨.

- **파이썬** 역시 **객체 지향 프로그램 언어**

  > `int()` 등도 객체를 나타냄

```python
- 인공지능 축구 프로그램을 작성한다고 가정
- 객체 종류 : 팀, 선수, 심판, 공
- Action : 선수 - 공을 차다, 패스하다
	   	   심판 - 휘슬을 불다, 경고를 주다
- Attribute : 선수 - 선수 이름, 포지션, 소속팀
			  팀 - 팀 이름, 팀 연고지, 팀 소속 선수
```

* OOP는 설계도에 해당하는 **클래스(class)**와 실제 구현체인 **인스턴스(instance)**로 나눔

![image-20220719160946997](C:\Users\msio9\OneDrive\취업\부스트캠프\boostcamp\pre-couse\object_oriented_programming\images\image-20220719160946997.png)

![image-20220719161041860](C:\Users\msio9\OneDrive\취업\부스트캠프\boostcamp\pre-couse\object_oriented_programming\images\image-20220719161041860.png)

## 파이썬으로 객체 구현하기(Objects in Python)

* 축구선수 정보를 Class로 구현하기

  ```python
  class SoccerPlayer(object):
      def __init__(self, name, position, back_number):
          self.name = name
          self.position = position
          self.back_number = back_number
  	def change_back_number(self, new_number):
          print("선수의 등번호를 변경합니다 : From %d to %d" % (self.back_number, new_number))
          self.back_number = new_number
  ```

* class 선언, object는 python3에서 자동 상속

  ![image-20220719161911692](C:\Users\msio9\OneDrive\취업\부스트캠프\boostcamp\pre-couse\object_oriented_programming\images\image-20220719161911692.png)

  > [알아두면 상식] Python naming rule
  >
  > > 참고[🔗 Naming Things: CamelCase vs snake_case - blog.lmorchard.com](https://blog.lmorchard.com/2013/01/23/naming-conventions/)
  >
  > - 변수와 Class명 함수명은 짓는 방식이 존재 
  >
  > - snake_case : 띄워쓰기 부분에 “_” 를 추가 
  >   뱀 처럼 늘여쓰기, 파이썬 함수/변수명에 사용
  > - CamelCase: 띄워쓰기 부분에 대문자 
  >   낙타의 등 모양, 파이썬 Class명에 사용

* Attribute 추가는 `__init__` , `self`와 함께! `__init__`은 **객체 초기화 예약 함수**

  ```python
  class SoccerPlayer(object):
      def __init__(self, name, position, back_number): # 객체를 초기화함.
          # self.으로 객체의 초기정보 선언
          self.name = name
          self.position = position
          self.back_number = back_number
  ```

  * `namedTuple`과 유사

*  `__`는 특수한 예약 함수나 변수 그리고 함수명 변경(맨글링)으로 사용
  예)  `__main__` , `__add__` , `__str__` , `__eq__`

  ```python
  class SoccerPlayer(object):
      def __str__(self): # 앞으로 print()문을 쓰게 되면 return에 있는 값이 출력됨.
          return "Hello, My name is %s. I play in %s in center " % (self.name, self.position)
      
  jinhyun = SoccerPlayer("Jinhyun", "MF", 10)
  print(jinhyun)
  ```

  

