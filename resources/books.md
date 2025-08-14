## [Python] 클래스(Class)

클래스란 말은 분야를 막론하고 정말 많이 쓰는것 같다. 그래서 더 헷갈릴 수 있으니 기록기록

과자를 찍어낸 틀=class(클래스)
찍어서 만들어낸 과자=object(객체)

클래스로 만든 객체에는 중요한 특징이 있는데,
각 객체마다 고유한 성격을 가진다.
즉, 하나의 과자를 베어먹는다 해서 다른 과자에 영향을 주지 않는다(독립)
#### 하나는 아이싱하고 다른 하나는 초코칩 붙여도 되는

ex) class Cookie:
       pass  # 클래스 안에 아무 내용이 없을 때는 pass

a = Cookie()   # 객체 생성
b = Cookie()
#### IDLE에서 클래스 정의를 끝내려면 pass 쓰고
#### 엔터 두 번 쳐서 들여쓰기 모드에서 빠져나와야 한다
(한 줄이라도 그냥 넘어가는 법이 없다)


### 예제) 사칙연산 클래스 만들기

클래스를 만들기 전에 먼저 어떻게 만들지 구상을 해보도록하자.

1. 사칙연산 클래스를 만들겠다.
2. 최소 2개의 숫자를 입력 받아야해 -> 두 숫자를 setdata(임의로 지은 이름임)에 넣자 = setdata 메서드 사용
3. 더하기 기능 필요->add 메서드(뭐뭐 메서드=걍 지은 이름)
5. 빼기-> sub메서드(substract: 빼다)
6. 나누기-> div메서드(divide)
7. 곱하기-> mul(multiply)


이제 구상했으니 얘네를 코드로 구현하면 된당.
#### 파이썬은 대소문자 구분한다. 똑똑한데?

1. 클래스 정의한다.
   class FourCal:
   
2. 데이터 저장 메소드
       def setdata(self, num1, num2):
   #### 클래스 안 메서드 첫 번째 인자는 항상 self라고 쓰는게 관례. 정의할땐 꼭 써야
          self.first = num1
          self.second = num2
   
3. 사칙연산 찍어내기
#### 코딩 괴담. 절대 스페이스, 엔터, 들여쓰기, 한 줄 비우기를 무의식적으로 하지 말것.. 
   def add(self): ####self만 호출
    result = self.num1+ self.num2
    return result
  
  def mul(self):
    result = self.num1 * self.num2
    return result

  def sub(self):
    result = self.num1 - self.num2
    return result

  def div(self):
    result = self.num1 / self.num2
    return result


4. 찍어내서 객체 만든다.
a=FourCal() -> ()가 붙으니 클래스란 뜻이다. FourCal틀을 이용해 a라는 새 객체를 만들겠다.
b=FourCal()
a.setdata(4,2)
b.setdata(3,8)

5. 계산 실행
#### ...는 사실상 같은 줄, >>> 될 때 한 줄씩 엔터하고 실행해야됨.
a.add()
6
b.add()
11
a.sub()
2





