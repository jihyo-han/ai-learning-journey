# Python Basics
## 2025-08-10
Q1. 홍길동의 과목별 점수는 다음과 같다. 홍길동 씨의 평균 점수는? 국어 - 80, 영어 -75, 수학 - 55
>>> a= 80
>>> b = 75
>>> c = 55

>>> print((a+b+c)/3)
#### print가 아니라 습관적으로 엑셀 함수(ave=)써버림
70.0

Q2. 자연수 13이 홀수인지 짝수인지 판별할 수 있는 방법?
>>> 13 % 2

 1

Q3. 홍길동의 주민등록번호는 881120-1068234이다. 홍길동의 주민등록번호를 연원일(YYYYMMDD)부분과 그 뒤의 숫자 부분으로 나누어 출력해보자
 
>>> pin = "881120-1068234"
>>> yyyymmdd = pin[:6]
>>> #### 정의할 때 pin 글자 빼먹음
>>> #### [:6]에서 6은 포함 안함
>>> num = pin[7:]
>>> print(yyyymmdd)
>>> print(num)

 881120
 1068234

Q4. 주민등록번호 뒷자리의 맨 첫 번째 숫자는 성별을 나타낸다. 성별을 나타내는 숫자를 출력해보자
>>> pin = "881120-1068234"
>>> print(pin[7])
#### 그냥 냅다 print[7]해버림. 결과는 오류. print( )구조
1

Q5. 다음과 같은 문자열 a:b:c:d가 있다. 문자열의 replace함수를 이용하여 a#b#c#d로 바꿔보자
a = "a:b:c:d"
#### 정의부터 틀림. 문자열이니까 " " 안에 넣어야지
>>> b = a.replace(":", "#")
바뀌는 주체가 ":","#" 얘네니까, a는 앞으로
>>> print(b)

a#b#c#d


Q6. [1, 3, 5, 4, 2] 리스트를 [5, 4, 3, 2, 1]로 만들어 보자.
>>> a = [1,3,5,4,2]
>>> a.sort()
>>> print(a)
#### 리스트 바꾸는거니까 b정의하지말고 a 바로 바꿈꿈

[1, 2, 3, 4, 5]

>>> a.reverse()
>>> print(a)

[5, 4, 3, 2, 1]

Q7. ['Life', 'is', 'too', 'short'] 리스트를 Life is too short 문자열로 만들어 출력해 보자.
>>> a = ['Life', 'is', 'too', 'short']
>>> b = " ".join(a)
#### 콤마가 아니고 (.)
>>> print(b)

Life is too short


Q8. (1,2,3) 튜플에 값 4를 추가하여 (1,2,3,4)를 만들어 출력해 보자.
>>> a = (1,2,3)
>>> b = a + (4,)
>>> print(a)

(1, 2, 3, 4)


Q9.  다음과 같은 딕셔너리 a가 있다. 다음 중 오류가 발생하는 경우를 고르고, 그 이유를 설명해 보자.
 a = dict()
 a
{}
a['name'] = 'python'
a[('a',)] = 'python'
a[[1]] = 'python'
a[250] = 'python'
-> 3번  : 리스트는 딕셔너리에 사용할 수 없다.

Q10. 딕셔너리 a에서 'B'에 해당되는 값을 추출해 보자. >>> a = {'A':90, 'B':80, 'C':70}
>>> a = {'A':90, 'B':80, 'C':70}
>>> result = a.pop('B')
#### B꺼내서 result에 넣음
>>> print(a)
>>> print(result)

{'A': 90, 'C': 70}
80


Q11. a 리스트에서 중복 숫자를 제거해 보자.
> a = [1, 1, 1, 2, 2, 3, 3, 3, 4, 4, 5]
>
>>> b = set(a)
#### 명령어(set)생각안남
>>> #이번엔 바뀌는 주체가 a니까 set(a)
>>> 
>>> list(b)
>>> #### print(b) → 집합(set) 형태로 출력 → {1, 2, 3, 4, 5}
>>> #### list(b) → 리스트로 변환한 뒤 출력 → [1, 2, 3, 4, 5]

#### 즉, list(aSet)는 자료형을 변환하는 거고,
#### print(aSet)는 그대로 출력하는 거예요.

 [1, 2, 3, 4, 5]


Q12. 파이썬은 다음처럼 동일한 값에 여러 개의 변수를 선언할 수 있다. 다음과 같이 a,b 변수를 선언한 후 a의 두 번째 요솟값을 변경하면 b 값은 어떻게 될까? 그리고 이런 결과가 오는 이유에 대해 설명해 보자.
>>> a = b = [1, 2, 3]
>>> print(b)

 [1, 4, 3]
  b가 a에 선언됐고 a의 1번째 리스트인 2가 4로 바뀌었으니, b는 [1,4,3]이 된다.


## 2025-08-11

Q1. 다음 코드의 결괏값은?
 

a  = "Life is too short, you need python"

if "wife" in a: print("wife")
#### 만약 wife가 a 안에 있으면 wife 출력--> 없음
elif "python" in a and "you" not in a: print("python")
#### 그렇지 않으면, python이 a 안에 있고, you가 a에 없으면 python출력-->아님
elif "shirt" not in a: print("shirt")
#### 그렇지 않으면, shirt가 a안에 없으면 shirt 출력-->shirt출력
elif "need" in a: print("need")
#### 그렇지 않으면-->전 단계 출
else: print("none")

#### 저기 a는 정의된 a인데 순간 관사로 착각


Q2. while문을 사용해 1부터 1000까지 자연수 중 3의 배수의 합을 구하라
 

result = 0
#### 처음에는 아무것도 더하지 않은 상태니까 0으로 시작
i = 1
#### 1부터
while i <= 1000:
#### 1000보다 작을동안 1000까지, :(문법주의, 들여쓰기)
  if i % 3 == 0:
  	result += i
   #### result = result + i 랑 같은의미 → 기존 result 값에 i를 더한 값을 다시 result에 저장
   #### result += i → 위랑 똑같은 의미지만 짧게 쓰는 축약 연산자
  i += 1
  #### 들여쓰기는 if랑 줄 맞춰야(이거 오류때문에 무한루프로 30분 날렸음ㅎ)
>>> print(result)
166833
#### 실행은 Ctrl + Alt + N

답: i%3==0


Q3. while문을 사용하여 다음과 같이 별(*)을 표시하는 프로그램을 작성해보자.
 
*
**
***
****
*****
i = 0
while True:
#### while문을 수행할 때 1씩 증가, 중간에 = 없음
  i += 1
  if #your code here:: break
  #### i값이 5를 초과하면 while 문을 벗어
  print(#your code here)

답: i > 5, '*'*i
#### print값이 신기한데 이렇게도 쓸 수 있네

Q4. for문을 사용해서 1부터 100까지의 숫자를 출력해라.
 
for i in range(1,101)
#### for문은 range함수와 함께 사용됨
#### range(시작숫자, 끝 숫자 미만)
  print(i)


Q5. A 학급에 총 10명의 학생이 있다. 이 학생들의 중간고사 점수는 다음과 같다.
[ 70, 60, 55, 75, 95, 90, 80, 80, 85, 100 ]
for문을 사용하여 A학급의 평균 점수를 구해보자.

A = [70,60,55,75,95,90,80,80,85,100]
total = 0

for score in A:
#### A리스트 안의 값을 하나씩 꺼내서 score라는 변수에 담음
  total += #your code here
#### 그 변수들을 이용해 계
average = #youre code here
#### 평균의 정의=total을 A의 길이(개수)로 나눔
print(average)

답: score, total/len(A)


Q6. 리스트 중에서 홀수에만 2를 곱하여 저장하는 다음과 같은 코드가 있다.
numbers = [1,2,3,4,5]
result = []
#### 결과를 담을 빈 리스트를 미리 만들어둠

for n in numbers:
  if n % 2 == 1:
    result.append(n*2)

 위 코드를 리스트 컴프리헨션(list comprehension)을 사용하여 표현해보자.
#### print 전까지 한줄로 만듦

numbers = [1,2,3,4,5]
result = [n*2 for n in numbers if n%2 == 1]
#### 위에 있던 result[]안에 결과 for 변수 in 집합 if 조건
print(result)




## 2025-08-12

Q1. 주어진 자연수가 홀수인지 짝수인지 판별해 주는 함수(is_odd)를 작성해 보자.
 

def is_odd(number):
  if #your code here:
    return True
  else:
    return False

답: number%2==1

#### lamda) is_odd=lamda x : True if x%2 == 1 else False

Q2. 입력으로 들어오는 모든 수의 평균 값을 계산해 주는 함수를 작성해보자. 
(단, 입력으로 들어오는 수의 개수는 정해져 있지 않다.)
 

def avg_numbers(#your code here):
  result = 0
  for i in args:
    result += i
  return #your code here

avg_numbers(1,2)
avg_numbers(1,2,3,4,5)

답: (1) *args
#### *은 꼭 필요(가변인자라는 뜻), args는 변수이름(근데 그냥 args많이 써)
    (2) return/len(args)


Q3. 다음은 두 개의 숫자를 입력받아 더하여 돌려주는 프로그램이다.
 

input1 = input("첫 번째 숫자를 입력하세요:")
input2 = input("두 번째 숫자를 입력하세요:")

total = input1 + input2
print("두 수의 합은 %s입니다." % total)
위 식에 대한 출력값이다. 

첫 번째 숫자를 입력하세요: 3
두 번째 숫자를 입력하세요: 6
두 수의 합은 36입니다.
3과 6을 입력했을 때, 9가 아닌 36을 반환했다.

이 프로그램의 오류를 수정해보자.

답: 3과 6을 문자로 인식. 입력은 항상 문자열(str)이므로 숫자(정수형)으로 바꿔주어야한다.
total=int(input1)+int(input2)
#### int(integer: 정수) -**실수(float)**도 정수로 변환 가능 (소수점 버림)
         -"3.5"처럼 소수점 있는 문자열은 int()로 바로 변환 불가 → 먼저 float()로 바꾼 후 int() 해야 함. a = int(float("3.5"))  # 3
#### int → integer → 정수형 (예: -2, -1, 0, 1, 2)
#### float → floating point number → 실수형 (예: -2.5, 0.0, 3.14)
#### str → string → 문자열




Q4. 다음 중 출력 결과가 다른 것 한 개를 골라보자
 

① print("you" "need" "python")
② print("you"+"need"+"python")
③ print("you", "need", "python")
④ print("".join(["you", "need", "python"]))

답: 3번. ,는 띄어쓰기로


Q5. 다음은 "text.txt"라는 파일에 "Life is too short" 문자열을 저장한 후 다시 그 파일을 읽어서 출려하는 프로그램이다.
 

f1 = open("test.txt", 'w')
f1.write("Life is too short")
#### 파일을 닫지 않고 바로열면 저장안됨
f1.close()
#### 이렇게 닫아줘

f2 = open("test.txt", 'r')
#### r도 ''안에 넣어줘. read라는 문자 약자니까

print(f2.read())
f2.close()
#### 여기도 닫아줘(메모리 누수 방지)

방법2) with사용(with블록을 벗어나는 순간 열린 파일이 자동으로 close되어 편리한 역할을 한다.)
with open("text.txt",'w') as f1:
    f1. write("Life is too short!")
with open("text.txt,'r') as f2:
    print(f2.read())
#### f1은 그냥 변수 이름. 연 파일을 담아둔 변수, 들여쓰기 4칸
#### f2.read() → 전체 읽기
     f2.readline() → 한 줄 읽기
     f2.readlines() → 모든 줄을 리스트로 읽기

   

### 파일 객체 = open(파일이름, 파일 열기 모드)
파일 열기 모드	설명
r	읽기 모드 - 파일을 읽기만 할 때 사용
w	쓰기 모드 - 파일에 내용을 쓸 때 사용
a	추가 모드 - 파일의 마지막에 새로운 내용을 추가할 때 사용
 

이 프로그램은 우리가 예상한 "Life is too short"라는 문장을 출력하지 않는다.

우리가 예상한 값을 출력할 수 있도록 프로그램을 수정해보자.

 

Q6. 사용자의 입력을 파일(test.txt)에 저장하는 프로그램을 작성해보자.
(단 프로그램을 다시 실행하더라도 기존에 작성한 내용을 유지하고 새로 입력한 내용을 추가해야한다.)
 

user_input = input("저장할 내용을 입력하세요 : ")
#### 실제 입력값
f = open('test.txt', #your code here)
f.write(user_input)
#### 변수이름
f.write(#your code here)
#### \n 입력하면 차곡차곡 내용 쌓임
f.close()

Tip. 기존의 내용을 유지하고 새로운 내용을 덧붙이기 위해서 'a' 추가모드를 사용한다.
Tip. 입력된 내용을 줄 바꿈(enter)하기 위해서 \n을 삽입한다

답: 'a', /n
 


Q7. 다음과 같은 내용을 지닌 파일 test.txt가 있다.
이 파일의 내용 중 'java'라는 문자열을 'python'으로 바꾸어서 저장해 보자.
 

Life is too short
you need java
 

f = open('test.txt', 'r')
#### f는 변수이름, 일단 파일 연다
body = #your code here
#### body도 변수이름, f 내용을 문자열로 읽어서 body라는 변수에 저장
f.close()
답: f.read

body = #your code here
답: body.replace('java','python')
#### body가 이미 파일 속 내용이 아니라 메모리 안의 문자열, 파일을 닫아도 body는 그대로 남아있음
그래서 열기 전에 바꾸기 가

f = open('test.txt', #your code here)
f.write(body)
f.close()
답: 'w'


Q8. 다음과 같이 실행할 때 입력값을 모두 더해 출력하는 스크립트(C:\doit\myargv.py)를 작성해보자
C:\>cd doit
C:\doit>python myargv.py 1 2 3 4 5 6 7 8 9 10

#### C:\>cd doit는 **윈도우 명령 프롬프트(cmd)**에서 쓰는 디렉터리 이동 명령어
#### C:\>현재 명령 프롬프트가 C: 드라이브의 **최상위 경로(루트)**에 있다는 표시
#### cd = change directory (폴더 이동)
doit라는 폴더로 이동하라는 뜻
#### python = 파이썬 실행
#### myargv.py = 실행할 파이썬 스크립트 파일

답:
import sys
#### sys 모듈을 불러옴

numbers = sys.argv[1:]
#### sys.argv[1:] 현재 실행 중인 파이썬 스크립트에 명령줄 인자를 리스트로 저장
#### 1부터 맞음. 0은 "myargv.py" 
#### sys.argv = ["myargv.py", "1", "2", "3", ...] 

result = 0
#### result → 합계를 저장하는 변수, 0으로 초기화
### 이거 계속 빼먹음
for number in numbers:
#### for number in numbers: → numbers 리스트에서 "1", "2", "3" 하나씩 꺼냄
#### 이거도 빼먹음..
    result += int(number)
  #### result = result + int(number) 의미, 문자를 숫자로 바꿔서 더
print(result)
#### 최종 합계 출력



## 2025-08-16

**__init__(self): 틀에 객체 찍어내자마자 실행시켜주

>>>class Dog:
    def __init__(self):  #언더바2개씩
        print("강아지 한 마리 태어남!")

>>>d=Dog()
강아지 한 마리 태어남!


Q1. 다음은 Calculator 클래스이다.

class Calculator:
 def __init__(self):
   self.value = 0

   #### self.value = 0의 의미
   self → “이 객체 자기 자신”
   value → 객체가 가진 변수 이
   = 0 → 객체가 처음 태어날 때 value를 0으로 만들어 줌
   👉 즉, 계산기의 초기값을 0으로 세팅하는 

   def add(self, val):
        self.value += val

#### val → 내가 더하고 싶은 숫자
self.value += val → 현재 값에다가 val을 더해서 다시 저장


위 클래스를 상속하는 UpgradeCalculator를 만들고 값을 뺄 수 있는 minus 메서드를 추가해보자.

즉 다음과 같이 동작하는 클래스를 만들어야 한다.

cal = UpgradeCalculator()
cal.add(10)
cal.munus(7)

print(cal.value) #10에서 7을 뺀  3을 출력

답:

class Calculator:
    def __init__(self):
        self.value = 0

    def add(self, val):
        self.value += val


class UpgradeCalculator(Calculator):   # Calculator 상속
    def minus(self, val):              # 새로 추가한 기능
        self.value -= val


cal = UpgradeCalculator()
cal.add(10)
cal.minus(7)        
print(cal.value)    #3

#### cal → 우리가 만든 객체
     value → 그 객체가 가지고 있는 속성(변수)
     . → “그 객체 안에 있는 걸 꺼내라”는 뜻


Q2. 객체변수 value가 100이상의 값은 가질 수 없도록 제한하는 MaxLimitCalculator 클래스를 만들어보자 


cal = MaxLimitCalculator()
cal.add(50)
cal.add(60)

print(cal.value)

단, 반드시 다음과 같은 Calculator클래스를 상속해서 만들어야한다.

class Calculator:
def __init__(self):
    self.value = 0

def add(self,val):
    self.value += val

class MaxLimitCalculator(Calculator):
  def add(self.val):
    self.value += val

  
    답: 아래 추가
    if self.value > 100:
      self.value = 100



Q3. 다음 결과를 예측해보자

1. all([1,2,abs(-3)-3])
답: False

1) abs 절댓값 반환
2) abs(-3)=3
3) [1,2,3-3]
4)  all([1,2,0)]
: all은 리스트 요소 중 0있으면 False 반환
-> all(iterable)은 모든 원소를 bool()로 바꿔서 다 참인지 확인
-> 파이썬에서 0은 거짓(False) 으로 취급


2. chr(ord('a'))=='a'
#### ord는 문자 -> 아스키 코드값 출력
#### chr는 아스키 코드값 -> 문자로 출력

1) ord('a') == 97
2) chr(97) == 'a'

답: True


Q4. filter와 lambda를 사용해서 리스트 [1,-2,3,-5,8,-3]에서 음수를 제거해보자.

#### filter: for문과 if문을 돌리는 것보다 간편하게 사용할 수 있다.

>>>list(filter(lamda x:x>0, [1,-2,3,-5,8,-3]))
[1, 3, 8]


Q5. 234라는 10진수의 16진수는 다음과 같이 구할 수 있다.
이번에는 반대로 16진수의 문자열  0xea를 10진수로 변경해보자.

>>> hex(234)
'0xea'

답:
>>> int('0xea', 16)
234

int
1) 문자형이나 실수형을 정수형으로 반환
2) int(x, radix): 진수변환0
int('0xea', 16): 0xea를 16진수로 변환



Q6. map과 lambda를 사용해서 [1,2,3,4] 리스트의 각 요솟값에 3이 곱해진 리스트 [3,6,9,12]를 만들어보자.

답:
>>> list(map(lamda x: x*3, [1,2,3,4]))



Q7. 다음 리스트의 최댓값과 최솟값의 합을 구해보자.
[-8, 2, 7, 5, -3, 5, 0, 1]

답:
>>> a = [-8,2,7,5,-3,5,0,1]
>>> max(a)+min(a)

-1


Q8. 17/3의 결과는 다음과 같다. 소숫점 4자리까지만 반올림해서 표시해보자.
>>> 17/3

5.6666666666666666666667

#### round() : 숫자를 반올림해서 반환
round(17/3)       # 6   (5.666...을 정수로 반올림)
round(17/3, 2)    # 5.67   (소수 둘째 자리까지 반올림)
round(2.675, 2)   # 2.67  

답: >>> round(17/3,4)

5.6667



Q9. 다음과 같이 실행할 때 입력값을 모두 더해서 출력하는 스크립트(C:\doit\myargv.py)를 작성

1) C:\cd doit로 이동한다
2) dir 명형을 실행하고 그 결과를 변수에 담는다.
3) dir 명령의 결과를 출력한다.
   
#### dir(directory) : 현재 디렉토리(폴더)에 들어 있는 파일과 하위 폴더 목록을 보여주는 명령

답:

import os                        # OS 기능 불러오기
os.chdir("C:\\doit")             # 작업 폴더 이동, chdir = change directory (폴더 바꾸기)
result = os.popen("dir")         # dir 실행 → 결과 문자열로 읽음
print(result.read())             # 결과 출력



Q10. glob모듈을 사용해서 C:\doit 디렉터리의 파일 중 확장자가 .py인 파일만 출력하는 프로그램을 만들어보자.


📌 문제에서 말하는 것

glob 모듈: 파이썬 내장 모듈 중 하나.

역할: 와일드카드 패턴(*, ?)을 써서 원하는 파일 이름만 골라줌.

문제 요구: C:\doit 폴더 안에 있는 파일 중
           확장자가 .py (파이썬 스크립트)인 파일만 찾기




✅ 풀이 코드

import glob → glob 모듈 불러오기


files = glob.glob("C:\\doit\\*.py")  # C:\doit 폴더에서 .py 확장자 파일만 찾기
                                       * = 모든 이름
print(files)

첫 번째 glob: 모듈 이름 (우리가 import glob으로 불러온 라이브러리)
두 번째 glob: 그 모듈 안에 들어있는 함수 이름
- 함수이름 확인
- dir() 함수로 확인
  import glob
  print(dir(glob))

- help() 함수로 확인
  import glob
  help(glob)



결과: 리스트 형태로 .py 파일들의 전체 경로가 들어옴



Q11. time모듈을 사용해서 현재 날짜와 시간을 다음과 같은 형식으로 "출력"해보자.
2018/04/03 17:20:32

답:
>>> import time
>>> now = time.strftime("%Y/%m/%d %H:%M:%S")  # time 모듈 안의 strftime(모듈 안에 들어있음) 함수 호출

#### strftime(): string format time - 현재 날짜·시간을 내가 정한 포맷 문자열("%Y-%m-%d %H:%M:%S")로 변환

print(now)

%Y = 년

%m = 월

%d = 일

%H = 시

%M = 분

%S = 초



Q13. random 모듈을 이용해서 로또번호(1~45사이의 숫자 6개)를 "생성"해보자. (중복 숫자 안 됨)


import random

- 파이썬 표준 모듈 random 불러오기.
- 랜덤 숫자 생성 관련 함수들(randint, shuffle, sample 등)을 쓸 수 있음

result = []
- 빈 리스트 생성
- 나중에 로또 번호 6개를 여기에 하나씩 넣을 예정.

while len(result) < 6:
- 반복문 시작.
- 즉, 숫자가 6개 모일 때까지 반복(숫자는 0부터 센다)

  num = random.randint(1,45)
- random → 우리가 import random 해서 불러온 모듈 이름
- randint → 그 안에 들어있는 함수 이름 (random integer)
- (1,45) → 함수에 넘기는 인자 (시작값, 끝값)

if num not in result:
- 뽑은 숫자(num)가 이미 result 리스트 안에 없는지 확인.

result.append(num)
- append = 리스트 뒤에 값 1개 추가

print(result)
