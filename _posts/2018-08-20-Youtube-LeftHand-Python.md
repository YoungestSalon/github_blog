---
title: "Youtube 왼손코딩 유기농냠냠파이썬"
date: 2018-08-20
tags: [Online Course, Youtube, LeftHand Coding, Python, Code, Cheatsheet, Data Science]
header:
  image: "/images/test/test.jpg"
excerpt: "Code Note"
mathjax: "true"
---
<br>
[Youtube 왼손코딩 유기농냠냠파이썬 인터넷 강의](https://www.youtube.com/watch?v=UHg1Drp1uKE&list=PLGPF8gvWLYypeEoFNTfSHdFL5WRLAfmmm)의 필기 정리 노트입니다.<br>
본 노트는 [GitHub](https://github.com/YoungestSalon/Outputs/blob/master/Online%20Course/Python_Youtube_LeftHand_1.md)에서도 확인 가능하십니다.

<br>
### **프로그래밍이 뭔가요?**

- 프로그램을 만드는 작업

<br>
### **프로그램**

- 문제를 해결하기 위한 명령을 모아놓은 것
- 순차구조(위에서부터 차례대로), 선택구조(조건에 따라 작동), 반복구조(반복됨)를 가지고 있음

<br>
### **왜 파이썬일까요?**

- 코드가 쉽고, 간결함 (다른 프로그래밍 언어에 비해)
- 자료가 많음 : 인터넷 커뮤니티, 참고자료 (Stack Overflow 등)
- 이미 만들어져 있는 코드가 많음 -> 개발 속도가 빠름

<br>
### **파이썬이 사용되는 곳**

- 프로그래밍 입문자가 처음 배우는 교육용 언어
- 구글 : 파이썬은 구글 3대 언어 중 하나, 파이썬 개발자가 구글에서 일했었음
- 유튜브. NASA
- 데이터 분석
- 게임 : 배틀필드, 문명 IV, 심즈4 등
- 보안, 해킹 등

<br>
### **파이썬 사용을 위한 준비**

- Python 3.x.x 사용 : [www.python.org에서](http://www.python.xn--org-k94n91q/) 설치 파일 다운로드 -> 설치

- Python 설치할 때 'Add Python 3.6 to PATH'를 체크해야 함

- Python 2.x.x와 3.x.x는 호환되지 않으며, 2.x.x는 추가 개발 계획이 없음

- 설치가 완료되면 IDLE(아이들 : 초보자를 위한 Python 프로그램)을 사용 가능

<br>
### **숫자형 & 연산자**

- 숫자형 : 정수, 실수 등. 연산 가능.
- 사칙연산 : + , - , * (Asterisk : 곱셈), / (Slash : 나눗셈)
- 사칙연산(심화) : ** (제곱), // (몫), % (나머지)
- 할당 연산자 : = (변수에 값을 할당하기 위해 사용)
- 복합 할당 연산자
  1. +=, -= 등
  2. 사칙연산의 결과값을 변수에 할당.
  3. 수식의 길이를 줄여줌

<br>
### **변수**

- 변수 : 값을 저장하는 공간.
- 변수에 할당한 값은 새롭게 지정할 수 있음. (즉, 변수의 값은 변경 가능)
- 변수 이름
  1. 어떤 자료인지를 알수 있어야 함
  2. 숫자로 시작하거나 공백 사용 불가능
  3. 대/소문자 구분함.

<br>
### **문자열 (String)**

- 따옴표(큰/작은)로 묶어서 생성 : 문자, 숫자 모두 사용 가능
- 숫자도 따옴표로 묶으면 문자열로 인식

  ~~~
  my_str1 = '3.14' : 3.14를 문자열로 인식
  ~~~

- print(type(변수 이름)) : 변수의 형태를 확인 가능 (Ex. print(type(my_str1))
- 연산자 : + (문자열을 합침), * (문자열을 반복. '문자열 * 문자열' 형태 불가.)

<br>
### **문자 가져오기 (인덱싱)**

- 문자열의 위치(인덱스)를 이용하여 하나의 문자를 가져오는 것.
- 주의 : 빈칸(공백)도 인덱스는 부여됨

  ~~~
  my_str2 = 'Hello Python'
  print(my_str2[5]) 		#결과 값 : 빈칸이 출력
  ~~~

- 앞 -> 뒤 : 0부터 시작 (Ex. print(my_str1[0]) )
- 뒤 -> 앞 : -1부터 시작

<br>
### **여러 개의 문자 가져오기 (슬라이싱)**

- [시작 인덱스 : 끝 인덱스+1] 형식

  ~~~
  my_str2 = 'Hello Python'
  print(my_str2[0:3]) 	#결과값 : Hel 출력
  ~~~

- 슬라이싱해도 원본 변수에는 변동 없음 (즉, Ctrl X+V가 아니라 Ctrl C+V임)
- 시작 인덱스 생략 : 처음부터 슬라이싱

  ~~~
  print(my_str2[:3]) == print(my_str2[0:3])
  ~~~

- 끝 인덱스 생략 : 시작 인덱스부터 끝까지 슬라이싱

  ~~~
  print(my_str2[6:] == print(my_str2[6:12]
  ~~~

<br>
### **함수 / 메소드**

- 함수 : 어떤 특정한 기능을 수행하는 코드의 모음
- 메소드 : 특정 자료형만 사용할 수 있는 함수

<br>
### **문자열 분리하기**

- 변수 이름.split() 함수 사용. (Ex. my_str3 = my_str2.split() )
- .split()의 결과로 생성된 변수는 리스트 자료형으로 인식
- .split() : 공백을 기준으로 분리
- .split(문자) : 해당 문자를 기준으로 분리

<br>
### **문자열 포맷팅**

- .format()
  1. 문자열을 좀 더 자유롭게 사용할 수 있게 해줌.
  2. 중괄호({})와 함께 사용.

  ~~~
  print('Life {} {}'.format('is', 'Short!'))
  # Life is Short! 가 출력
  ~~~

<br>
### **여러줄 문자열**

- 따옴표를 세 번 사용. (즉, '''문자열''' 혹은 """문자열""" 의 형태)
- 따옴표를 한 번 사용 : 한 줄 문자열만 표현 가능

<br>
### **출력의 끝 지정하기**

- print('', end = '') 형태로 사용
- print('문자열', end='') : 문자열 출력 후 줄 바꿈이 없어짐
- print('문자열', end='-') : 문자열 출력 후 줄 바꿈 대신 '-'가 붙음
- print('문자열', end='\n') : 문자열 출력 후 줄 바꿈 (즉, 기본값과 동일)
- print('문자열', end='\t') : 문자열 출력 후 줄 바꿈 대신 Tab 추가

<br>
### **C 스타일 포맷팅**

- '{}'.format() 형태의 format 메소드 대신 %를 사용하는 연산자로도 문자열 포맷팅이 가능
- %d : 정수 (Ex. print('%d x %d = %d' % (2, 3, 6) )
- %f : 실수
- %s : 문자열 (Ex. print('Life is %s' % 'Short!') )

<br>
### **이스케이프 코드**

- 특정한 기능을 수행하는 문자의 조합. 문자열에 포함해서 사용 가능.
- \n : 줄 바꿈. (Ex. print('줄바꿈\n줄바꿈') : 줄바꿈 사이에 줄이 바뀜)
- \t : Tab. (Ex. print('탭\t탭') : 탭과 탭 사이에 Tab 빈칸이 들어감)
- '\n'을 출력하고 싶은 경우 : print('\n')
- '\t'를 출력하고 싶은 경우 : print('\t')
- 작은 따옴표를 문자로 쓰고 싶은 경우에도 사용 (Ex. print('I'm yours') = I'm yours)

<br>
### **주석**

- 사람을 위해 어떠한 설명을 기재하는 것. 컴퓨터는 볼 수 없고, 무시함.
- '#' 문자를 사용. # 뒤에 있는 내용은 모두 주석 처리가 됨.

<br>
### **재료 모으기 : 리스트**

- '변수명 = [요소1, 요소2, 요소3 ...]' 형식 (Ex. my_list = ['a', 'b', 'c', 'd']
- 여러 개의 값을 한 곳에 모아 관리(저장/제어 등) 가능
- 리스트 안에 구성 요소로 리스트를 넣을 수 있음
- 빈 리스트 생성 가능 ('변수명 = []')
- 인덱싱 가능 : 각 요소마다 0부터 시작하는 인덱스 생성됨. (Ex. print(my_list[0]))
- 슬라이싱 : 10번의 슬라이싱과 동일. 슬라이싱해도 원본 리스트에는 변동 없음.

<br>
### **리스트에서 사용할 수 있는 문법(메소드 등)**

- 값 추가 : 변수명.append() 메소드 사용. (Ex. my_list.append(123))
- 값 변경 : 인덱싱 활용. (Ex. my_list[0] = 3.14 -> my_list의 첫 번째 요소가 3.14로 변경)
- 값 삭제 : del 키워드 활용. 각 요소의 인덱스가 앞으로 당겨짐. (Ex. del my_list[0])
- 값 정렬 : 변수명.sort() 메소드 사용. 숫자/문자 모두 사용 가능. 오름차순으로 정렬됨.
- 값 개수 세기 : 변수명.count() 메소드 사용. (Ex. print(my_list.count('a')) : a의 개수를 셈)
- 값의 존재 유무 확인 : in(있는지), not in(없는지) 사용. 논리형(Boolean)으로 결과값 출력.

  ~~~
  print('f' not in my_list)
  print('f' in my_list)
  ~~~

<br>
### **튜플**

- 리스트와 거의 비슷(여러 개의 값을 모아 저장 + 값의 순서가 있음) but 값 수정 불가능(Immutable).
- '변수명 = (요소1, 요소2, 요소3 ...)' 또는 '변수명 = 요소1, 요소2, 요소3 ...' 형식
- 값이 1개인 경우, 마지막은 ',)' 로 처리. 사칙연산의 소괄호와 혼동을 막기 위함. (Ex. my_tuple1 = (1,))
- 다양한 자료형을 동일한 튜플에 한꺼번에 집어넣을 수 있음 (Ex. my_tuple2 = 3.14, 'Python', True)
- 튜플을 사용하는 이유 : 변경되면 안되는 값을 저장, 리스트에 비해 속도가 빠름, 파이썬 문법 특성상 은연중에 이미 사용하고 있음(?!)

<br>
### **우리는 어떤 튜플을 사용하고 있었을까?**

- 패킹 : 여러 개의 값을 하나로 묶는 것 (Ex. my_tuple2 = 3.14, 'Python', False)
- 언패킹 : 묶여 있는 여러 값을 풀어 내는 것 (Ex. i, s, b = (123, 'abc', True))

<br>
### **횟수 기준 반복문 (for문)**

- 반복문 : 반복되는 작업을 처리할 수 있는 구문 (조건 기준 : while / 횟수 기준 : for)
- for문

  ~~~
  for 변수 in 순서열:
      실행할 명령
  ~~~

  ~~~
  for count in my_list:
      print('횟수:', count))
  ~~~

- for문 중첩 가능 : 엑셀에서 if 함수 중첩하는 것과 동일한 원리.
- 문자열 반복 : for문의 순서열 부분을 문자열로 입력.

  ~~~
  my_str = 'coding'

  for letter in my_str
      print('문자:', letter)
  ~~~

- range(start, stop) : 숫자를 입력 받아서 순서열을 만들어주는 함수.

  ~~~
  for count in range(0, 3)
     print('횟수:', count)
  ~~~

- Comprehension (리스트 내포) : 리스트 + for문. 리스트가 간결해짐.

  ~~~
  odd_numbers = [number for number in numbers if number % 2 == 1]
  ~~~

<br>
### **조건 판단하기**

- 논리형(Boolean) : 참(True) or 거짓(False). 비교 연산자/논리 연산자의 결과로 많이 사용.
- 비교 연산자 : 여러 값을 비교하는 연산자.

  ~~~
  == (같음?), != (다름?), > (큼?), < (작음?), >= (크거나 같음?), <= (작거나 같음?)
  ~~~

- 비교 연산자는 중복이 가능하며, 결과는 논리형으로 저장 (Ex. my_cmp1 = 1 <= 2 < 3 : True로 저장)
- 논리 연산자 : 세 가지 종류(and, or, not). 결과는 논리형으로 저장.
- and : 둘 다 True여야 결과가 True (Ex. my_con1 = 1 < 2 and 2 < 1 : False로 저장)
- or : 둘 중 하나만 True여도 결과가 True (Ex. my_con2 = 1 < 2 or 2 < 1 : True로 저장)
- not : True/False간 reverse 처리 (Ex. my_con3 = not 1 == 1 : True의 반대, 즉 False로 저장)

<br>
### **조건문**

- if : 조건의 참/거짓 여부에 따라 처리의 흐름을 바꿀 수 있음

  ~~~
  if 조건:
  	실행할 명령
  ~~~

  ~~~
  name = 'Lefty'
  if name == 'Lefty'				#조건문 : 이름이 Lefty인가?
      print('당신이 Lefty군요.')
      print('만나서 반가워요.')
  ~~~

- if - else : 조건이 참이면 if의 명령을, 거짓이면 else의 명령을 실행

  ```
  if 조건:
      실행할 명령
  else:
      실행할 명령
  ```

- if - elif : if의 조건이 참이면 명령을 실행, 거짓이면 elif의 조건을 판단하여 실행

  ~~~
  if 조건:
      실행할 명령
  elif 조건:
      실행할 명령
  else:
      실행할 명령
  ~~~

  ~~~
  name = 'Alice'
  if name == 'Alice':				#이름이 Alice인가?
      print('당신이 Alice군요.')
  elif name == 'Bob':				#이름이 Alice가 아니라면, Bob인가?
      print('당신이 Bob이군요.')
  else:						   #이름이 Alice도 Bob도 아니라면.
      print('당신은 누구십니까?')
  ~~~

<br>
### **조건 기준 반복문 (while문)**

- while문 : 조건이 참인 동안은 명령을 반복함
- continue :  다시 조건문으로 돌아감. 하단의 명령 수행은 생략.

  ~~~
  while 조건:
      실행할 명령
  ~~~

  ~~~
  count = 0
  while count < 5:
      count = count + 1
      if count % 2 == 1:
          continue
      print(count)
  ~~~

- while True : 조건이 무조건 참인 반복문 = 무한 반복하는 while문 (무한 루프)
- break : 반복문을 종료시킴

  ~~~
  while True:
      name = input('당신의 이름은?')
      if name == '종료':
          print('종료합니다.')
          break
      print('{}님, 안녕!'.format(name))
  ~~~

<br>
### **입력받기**

- input() 함수 : 프로그램 실행 중에 사용자의 입력을 받는 함수
- input() 함수로 입력 받은 값은 항상 문자열로 저장

  ~~~
  name = input('이름을 입력하세요:')
  ~~~

<br>
### **자료형**

- 확인 : type() 함수 (자료형을 확인하는 함수)

  ~~~
  name = input('이름을 입력하세요:')
  print('안녕, {}!'.format(name))
  print(type(name))
  ~~~


- 변경 : int() (정수형), str() (문자열), float() (실수형), list() (리스트로 변경)

  ~~~
  age = int(input('나이를 입력하세요:'))
  print('{}살 이시군요!'.format(age-3))
  ~~~

<br>
### **재료 모으기 : 딕셔너리**

- 리스트/튜플 : 자료가 많아지면 인덱싱으로 특정 값에 접근하기 어려움.
- 딕셔너리 : 리스트/튜플과 유사하나, 인덱스 대신 키를 사용

  ~~~
  {키1:값1, 키2, 값2, ...}
  ~~~

- 딕셔너리의 키 : 값을 변경할 수 없는 자료형만 가능 (숫자, 문자열, 튜플 등)
- 딕셔너리의 값 : 전부 다 사용 가능, 딕셔너리 안에 딕셔너리를 넣을수도 있음

  ~~~
  my_dict1 = {1: 'a', 2: 'b'}
  my_dict2 = {'a': 1, 'b': 2}
  my_dict3 = {1: 'a', 'b': 2}
  ~~~

- 값 추가 : '딕셔너리명[키] = 값' 형식

  ~~~
  my_dict = {}		#빈 딕셔너리를 생성
  my_dict[1] = 'a'
  my_dict['b'] = 2
  my_dict['c'] = 'd'
  ~~~

- 값 접근 : '딕셔너리명[키]' 형식. 리스트의 인덱스와 원리는 동일.

  ~~~
  my_dict = {1: 'a', 'b': 2, 'c': 'd'}
  print(my_dict[1])
  print(my_dict['b'])
  print(my_dict['c'])
  ~~~

- 값 삭제 : del 키워드 사용. 'def 딕셔너리명[키]' 형식.

  ~~~
  my_dict = {1: 'a', 'b': 2, 'c': 'd'}
  del my_dict[1]
  del my_dict['b']
  del my_dict['c']
  ~~~

- 값만 묶어서 가져오기 : .values() 메소드 사용. '딕셔너리명.values()' 형식.

  ~~~
  my_dict = {'k1': 'v1', 'k2': 'v2'}
  for val in my_dict.values():
      print(val)
  ~~~

- 키만 묶어서 가져오기 : .keys() 메소드 사용. '딕셔너리명.keys()' 형식.

  ```
  my_dict = {'k1': 'v1', 'k2': 'v2'}
  for key in my_dict.keys():
      print(key)
  ```

- 키/값을 모두 가져오기 : .items() 메소드 사용. '딕셔너리명.items()' 형식.

  ```
  my_dict = {'k1': 'v1', 'k2': 'v2'}
  for key, val in my_dict.items():	#키와 값의 변수가 각각 필요
      print(key, val)
  ```

<br>
### **모아서 다시쓰기 (함수)**

- 함수 : 반복되는 코드를 묶어서 이름을 붙인 것

  ~~~
  #사용자 정의 함수를 만드는 방법

  def 함수이름(인자1, ...):		  #인자 : 없어도 되고, 여러개여도 됨
      실행할 명령 1
      실행할 명령 2

      return 결과1, 결과2, ...    #결과 : 없어도 되고, 여러개여도 됨
  ~~~

  ~~~
  def my_sum_mul(n1, n2):
      return n1 + n2, n1 * n2

  s, m = my_sum_mul(2, 3)
  print(s)
  print(m)

  result = my_sum_mul(2, 3)
  result
  #'(5, 6)' 출력 : 함수의 결과는 패킹돼서 튜플 형태의 한 값으로 나옴
  #위에서 s, m으로 함수의 결과를 받으면서 언패킹을 진행함
  ~~~


- 함수의 종류
  1. 내장 함수 : 파이썬에 포함되어 있는 함수. 별도 생성 작업 필요 없음.
  2. 모듈의 함수 : 다른 곳에서 이미 만들어 놓은 함수.
  3. 사용자 정의 함수 : 우리가 직접 만든 함수.


- 함수를 사용하는 이유
  1. 다시 사용할 수 있음 : 시간/노동력의 측면에서 효율적
  2. 코드를 관리하기 쉬워짐
  3. 조립해서 사용할 수 있음


- Docstring (Documentation String)
  1. 문서화 문자열
  2. 주석 중 한 가지로, 함수 바로 아랫줄에 기재하여 함수의 기능을 설명
  3. 큰 따옴표 3개(""")를 주로 사용.

     ~~~
     def sum_mul(num1, num2):
         """입력 값을 더하고 곱합니다."""	#Docstring
         return num1 + num2, num1 * num2
     ~~~


- 모듈
  1. 비슷한 함수들을 모아둔 파일.
  2. import 키워드로 가져옴
  3. '.'을 이용해서 모듈에 포함된 함수를 사용할 수 있음
  4. 종류 : 파이썬 기본 제공 모듈, 다른 사람/회사가 만든 모듈 등.
  5. '있는 바퀴를 다시 만들지 말아라' : 모듈을 적절히 활용하자!


- Random 모듈
  1. 난수 생성, 무작위와 관련된 함수를 포함하고 있는 모듈
  2. .choice() 함수 : 리스트에 포함된 값 중 하나를 랜덤하게 뽑아냄

     ~~~
     import random
     fruits = ['apple', 'banana', 'lemon']
     my_fruits = random.choice(fruits)
     print(my_fruit)
     ~~~

  3. .sample() 함수 : 리스트에서 x개의 값을 중복 없이 선택함

     ~~~
     import random
     fruits = ['apple', 'banana', 'lemon']
     my_fruits = random.sample(fruits, 2)	#2개를 중복 없이 선택
     print(my_fruit)
     ~~~

  4. .randint() 함수 : 정해진 정수 범위 내에서 정수 하나를 랜덤하게 선택함

     ~~~
     import random
     my_int = random.randint(0, 10)
     print(my_int)
     ~~~

<br>
### **객체**

- 현실의 사물을 컴퓨터 안에 재현한 것
- 파이썬은 대부분이 객체임 (Ex. 리스트 : 데이터 + 함수(= 메소드))
- 함수와 데이터를 한꺼번에 묶어서 표현
- 객체가 가지고 있는 데이터 + 취할 수 있는 행동
<br>
