
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






## 내장함수 특집
Don't Reinvent The Wheel!
이미 있는 것을 다시 만드느라 쓸데없이 시간을 낭비하지 말라.

파이썬 내장함수는 다른 외부 모듈과 달리
import를 시키지 않고 바로 사용할 수 있다.

파이썬의 내장함수 종류가 엄청 많은데
이를 다 외울 수는 없고,
나중에 찾아 활용할 수 있을 정도로 기억해두는 것이 좋다.

### abs 절댓값

### all
x가 모두 참이면 -> Ture
x가 하나라도 거짓이면 -> Flase

>>> all([1,2,3])
Ture
>>> all([1,2,3,0])
False
- 숫자형에서 0은 False이다.

scores = [80, 90, 75, 100]
print(all(score >= 90 for score in scores))  
False → 75, 80



### any
x가 하나라도 참 -> True
x가 모두 거짓 -> Flase

### chr
chr(i)는 아스키 코드값을 입력받아 그 코드에 해당하는 문자를 출력
아스키 코드란? 0~127사이 숫자를 각 하나의 문자나 기호에 대응 시켜 놓은 것
>>> chr(97)
'a'
>>> chr(42)
'*'

### dir
dir(물건) → 그 물건이 가진 버튼·기능 목록을 보여줌.
"이거로 뭘 할 수 있는지 싹 다 보여줘!" 버튼 🚀

>>> dir(list)
['__add__',
 '__class__',
 '__contains__',
 '__delattr__',
 '__delitem__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__gt__',
 '__hash__',
 '__iadd__',
 '__imul__',
 '__init__',
 '__init_subclass__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__mul__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__reversed__',
 '__rmul__',
 '__setattr__',
 '__setitem__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'append',
 'clear',
 'copy',
 'count',
 'extend',
 'index',
 'insert',
 'pop',
 'remove',
 'reverse',
 'sort']

list에서 사용할 수 있는 메소드의 목록들이 리턴된다.

### divmod
divmod(a,b)는 2개의 숫자를 입력받는다.
그리고a와 b를 나눈 몫과 나머지를 튜플 형태로 반환한다.

>>> divmod(7,5)

(1, 2)

### enumerate
: 열거하다
: 반복문(for) 돌릴 때, 번호까지 같이 주는 친구

fruits = ["사과", "바나나", "체리"]

for i, fruit in enumerate(fruits, start=1):
    print(i, fruit)

1 사과
2 바나나
3 체리

- i는 번호(보통 0부터 시작, start=1이니까 1부터 시작)
    


### eval
실행 가능한 "문자열" 을 입력받고
문자열을 실행한 한 결괏값을 돌려준다.

>>> eval('1+2')

3

>>> eval("'hi'+'a'")

'hia'

### filter
인공지능에서 전처리 할 때 사용을 많이 한다.
1) 그냥 for 문 출력

numbers = [1, 2, 3, 4, 5]

evens = []

for n in numbers:
     if n % 2 == 0: 
        print(n)
>>>2
>>>4
➡ 화면에만 보여주고, **집에 가져올 바구니(리스트)**는 없음.

vs

2) filter(검사기준, 원래있던 모든 물건) 사용
numbers = [1, 2, 3, 4, 5]

def is_even(n):
 return n % 2 == 0

 result = filter(is_even, numbers)   # 짝수만 걸러서 result 객체 생성

 print(list(result))   # list()로 변환해야 내용 확인 가능
 
 
### hex
 정수값을 입력받고-> 16진수로 변환하여 리턴

### id
객체를 입력받아서 객체의 고유 주소값을 리턴

>>> a = 3
>>> id(3)
93851867576896

>>> id(a)
93851867576896

>>> b = a
>>> id(b)
93851867576896


위 코드를 보면 3과 a와 b의 고유 주소 값이 93851867576896인 것을 볼 수 있다.
= 이는 3과 a와 b가 모두 같은 객체임을 확인할 수 있는 방법이다.


### input
a=input()
hi
print(a)
hi # a 안에 hi라는 '문자열' 저장

ex)
b=input("아무 말이나 입력하세요:")
아무 말이나 입력하세요:bye <- 입력안내문 역할
print(b)
bye


### int
문자열 형태 숫자/소수점 숫자 -> 정수 형으로 리턴

### isinstance
이게 내가 원하는 타입 맞아?" 하고 물어보는 검사기

print(isinstance(5, int))          # True (5는 정수)
print(isinstance("hi", str))       # True ("hi"는 문자열)
print(isinstance([1, 2, 3], list)) # True (리스트 맞음)
print(isinstance(3.14, int))       # False (실수지 정수가 아님)



### len
길이(요소의 전체 개수)를 돌려주는 함수

### list

###

###

###

###

###



