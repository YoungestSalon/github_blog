---
title: "Inflearn Pandas 팬더스 데이터분석 기초 실습"
date: 2018-08-21
tags: [Online Course, Inflearn, Pandas, Code, Cheatsheet, Data Science]
header:
  image: "/images/test/test.jpg"
excerpt: "Code Note"
mathjax: "true"
---
<br>
[Pandas 팬더스 데이터분석 기초 실습 강의](https://www.inflearn.com/course/pandas-%ED%8C%AC%EB%8D%94%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D-%EA%B8%B0%EC%B4%88/) Code Note입니다.
<br><br>
*참조 : 실습에 사용되는 예제 파일, 코드는 [GitHub](https://github.com/minsuk-heo/pandas/blob/master/Pandas_Cheatsheet.ipynb)에서 확인 가능합니다.* <br>
*참조 : 본 Notebook은 Jupyter Notebook 환경에서 작성됐으며, [GitHub](https://github.com/YoungestSalon/Outputs/blob/master/Online%20Course/inflearn_pandas/Inflearn_Pandas_Code_note.ipynb)에서도 확인 가능합니다.*
<br><br>
### 1강 : Pandas가 무엇인가요?

- Pandas?
  - 파이썬 라이브러리.
  - 데이터를 목적에 맞게 수정/변경할 때 중요하게 사용됨



- 마이크로소프트 엑셀이 있는데 왜 굳이 팬더스를...?
  - 엑셀 : 프로그램을 만들 수 없음.
  - 팬더스 : numpy를 사용하기 때문에 숫자 계산의 performance가 빠르고 강력함.



- 팬더스의 구성 요소들
  - 시리즈(Series) : 각각의 컬럼(Column)을 시리즈라고 부름. 파이썬 리스트로 만들어짐.
  - 데이터프레임 = 시리즈의 결합체. (즉, 시리즈의 합)


```python
import pandas as pd
```


```python
data_frame = pd.read_csv('data/friend_list.csv')
```


```python
data_frame
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_frame.head(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_frame.tail(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
type(data_frame.name)
```




    pandas.core.series.Series




```python
list_tmp = [1,2,3]
```


```python
list_tmp
```




    [1, 2, 3]




```python
s1 = pd.core.series.Series( [1,2,3] )
```


```python
s2 = pd.core.series.Series( ['one', 'two', 'three'] )
```


```python
pd.DataFrame(data=dict(num=s1, word=s2))
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>num</th>
      <th>word</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>one</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>two</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>three</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 2강 : 파일에서 데이터 불러오기


```python
# 팬더스가 깔려 있는지 여부를 확인

!conda list | grep pandas
```

    pandas                    0.23.0           py36h830ac7b_0  



```python
import pandas as pd
```


```python
# 실습1 : 첫번째 행에 header가 들어있는 csv 파일을 불러오기

df = pd.read_csv('data/friend_list.csv')
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터의 가장 앞에 있는 2개만 보여줌

df.head(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터의 가장 마지막에 있는 3개만 보여줌

df.tail(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 실습2 : 쉼표(,)로 구분하여 정리되어 있는 txt 파일을 불러오기

df = pd.read_csv('data/friend_list.txt')
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 실습3 : Tab으로 구분하여 정리되어 있는 txt 파일을 불러오기
# 구분자가 Tab이라는 사실을 알려줘야 함 : delimiter option 추가

df = pd.read_csv('data/friend_list_tab.txt', delimiter = '\t')
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 실습4 : 칼럼의 이름(Header) 정보가 없는 csv 파일을 불러오기
# Header가 없다는 사실을 알려줘야 함 : header = None 이라는 option을 추가

df = pd.read_csv('data/friend_list_no_head.csv', header = None)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 칼럼의 이름을 정해주려면

df.columns = ['name', 'age', 'job']
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 실습5 : 칼럼의 이름(Header) 정보가 없는 csv 파일을 불러옴 + Header도 한번에 추가

df = pd.read_csv('data/friend_list_no_head.csv', header = None, names = ['name', 'age', 'job' ])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 3강 : Create DataFrame from your python code

- 팬더스에서 데이터프레임을 만들때
  - 파이썬의 딕셔너리를 활용 : Ordered Dictionary
  - 파이썬의 리스트를 활용


```python
import pandas as pd
```


```python
# 파이썬 딕셔너리를 생성

friend_dict_list = [
    {'name': 'John', 'age': 25, 'job': 'student'},
    {'name': 'Nate', 'age': 30, 'job': 'teacher'}    
]
```


```python
# 딕셔너리를 이용하여 팬더스 데이터프레임을 생성

df = pd.DataFrame(friend_dict_list)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>student</td>
      <td>John</td>
    </tr>
    <tr>
      <th>1</th>
      <td>30</td>
      <td>teacher</td>
      <td>Nate</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 딕셔너리를 이용하여 데이터프레임을 생성할 시, 칼럼 순서가 바뀔 수 있음
# 딕셔너리는 이름-나이-직업 순서 but 데이터프레임은 나이-직업-이름 순서
# 데이터프레임의 칼럼 순서를 수동으로 변경해줘야 하는 단점이 있음

df = df[['name', 'age', 'job']]
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>25</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 순서를 유지하며 데이터프레임 만들기 : 파이썬에서 제공하는 Ordered Dictionary를 활용.
# Ordered Dictionary 사용을 위한 사전 준비가 필요.

from collections import OrderedDict
```


```python
# Ordered Dictionary : 딕셔너리 Key의 순서를 보장함
# Ordered Dictionary 만들기

friend_ordered_dict = OrderedDict(
    [        
        ('name', ['John', 'Nate']),
        ('age', [25, 30]),
        ('job', ['student', 'teacher']),        
    ]    
)
```


```python
# 생성된 Ordered Dictionary로 데이터프레임 만들기

df = pd.DataFrame.from_dict(friend_ordered_dict)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>25</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 이번에는 파이썬 리스트를 사용하여 데이터프레임을 만들어보자

friend_list = [
    ['John', 25, 'student'],
    ['Nate', 30, 'teacher']
]
```


```python
# Column Header 정보 만들어주기

column_name = ['name', 'age', 'job']
```


```python
# 생성한 리스트로 데이터프레임 만들기

df = pd.DataFrame.from_records(friend_list, columns = column_name)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>25</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Column Header를 별도로 만들지 않으면서 리스트로 데이터프레임 생성하기 예시.
# 리스트 안의 리스트 기능을 활용하면 됨

friend_list = [
    ['name', ['John', 'Nate']],
    ['age', [25, 30]],
    ['job', ['student', 'teacher']]    
]
```


```python
# 생성한 리스트로 데이터프레임 만들기

df = pd.DataFrame.from_items(friend_list)
```

    C:\ProgramData\Anaconda3\lib\site-packages\ipykernel_launcher.py:3: FutureWarning: from_items is deprecated. Please use DataFrame.from_dict(dict(items), ...) instead. DataFrame.from_dict(OrderedDict(items)) may be used to preserve the key order.
      This is separate from the ipykernel package so we can avoid doing imports until



```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>25</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 4강 : Write DataFrame to File (데이터프레임 파일로 저장하기)


```python
import pandas as pd
```


```python
# 데이터프레임을 생성

friends = [{'name': 'Jone', 'age': 20, 'job': 'student'},
          {'name': 'Jenny', 'age': 30, 'job': None},
          {'name': 'Nate', 'age': 30, 'job': 'teacher'}]
df = pd.DataFrame(friends)
df = df[['name', 'age', 'job']]
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>None</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터프레임을 csv 파일로 저장
# df.to_csv('friends.csv', index = True, header = True)이나,
# index와 header는 default setting이 True이므로 이 경우에는 생략해도 무관함.
# row ID를 생략하고 싶은 경우 : index = False
# column name을 생략하고 싶은 경우 : header = False

df.to_csv('friends.csv')
```


```python
# 데이터프레임을 csv 파일로 저장할 때, None 값은 기본적으로 빈 칸으로 저장됨.
# None 값에 빈 칸 대신 다른 option을 주고 싶다면 na_rep로 지정해줘야 함.

df.to_csv('friends.csv', index = False, header = False, na_rep = '-')
```
<br>
### 5강 : Pandas - Select, Filter Rows or Columns (행/열 선택, 필터)


```python
import pandas as pd
```


```python
# 데이터프레임을 생성

friend_list = [
                ['name', ['John', 'Jenny', 'Nate']],
                ['age', [20, 30, 30]],
                ['job', ['student', 'developer', 'teacher']]
              ]
df = pd.DataFrame.from_items(friend_list)
```

    C:\ProgramData\Anaconda3\lib\site-packages\ipykernel_launcher.py:6: FutureWarning: from_items is deprecated. Please use DataFrame.from_dict(dict(items), ...) instead. DataFrame.from_dict(OrderedDict(items)) may be used to preserve the key order.




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Jenny, Nate의 row만 선택해서 보려면?
# 파이썬 인덱스 : 첫번째 인덱스는 포함, 마지막 인덱스는 제외. (= 1은 포함, 3은 제외)

df[1:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 단, df라는 데이터프레임에서 John의 row가 삭제된 것은 아님.

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# df라는 데이터프레임에서 John의 row를 삭제하려면?
# John을 제외하고 Jenny, Nate만 선택한 후 저장하면 됨

df = df[1:3]
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터프레임을 다시 생성

friend_list = [
                ['name', ['John', 'Jenny', 'Nate']],
                ['age', [20, 30, 30]],
                ['job', ['student', 'developer', 'teacher']]
              ]
df = pd.DataFrame.from_items(friend_list)
df
```

    C:\ProgramData\Anaconda3\lib\site-packages\ipykernel_launcher.py:8: FutureWarning: from_items is deprecated. Please use DataFrame.from_dict(dict(items), ...) instead. DataFrame.from_dict(OrderedDict(items)) may be used to preserve the key order.






<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 불연속적인 row만 선택해서 보려면? (Ex. John, Nate)

df.loc[ [0,2] ]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 불연속적인 row만 선택해서 저장하려면? (Ex. John, Nate)

df = df.loc[ [0,2] ]
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>



### Filter by column condition


```python
# 데이터프레임을 다시 생성

friend_list = [
                ['name', ['John', 'Jenny', 'Nate']],
                ['age', [20, 30, 30]],
                ['job', ['student', 'developer', 'teacher']]
              ]
df = pd.DataFrame.from_items(friend_list)
df
```

    C:\ProgramData\Anaconda3\lib\site-packages\ipykernel_launcher.py:8: FutureWarning: from_items is deprecated. Please use DataFrame.from_dict(dict(items), ...) instead. DataFrame.from_dict(OrderedDict(items)) may be used to preserve the key order.






<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Column의 condition에 따라 row를 선택하는 방법 (1/2)
# 예시: 나이가 25세 이상인 row만 선택하고 싶다면?

df[df.age > 25]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Column의 condition에 따라 row를 선택하는 방법 (2/2)
# 예시: 나이가 25세 이상인 row만 선택하고 싶다면?

df.query('age>25')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 2개 이상의 정보를 기준으로 row를 선택하는 방법
# 예시 : 나이가 25세 이상이고, 이름이 Nate인 row만 선택하고 싶다면?

df[ (df.age>25) & (df.name == 'Nate') ]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>



### Filter Column




```python
# Filter Column by Index
# 일단 예시 데이터부터 만든다.

friend_list = [
    ['John', 20, 'student'],
    ['Jenny', 30, 'developer'],    
    ['Nate', 30, 'teacher']    
]
df = pd.DataFrame.from_records(friend_list)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 만약 모든 Column을 선택하려면 df.iloc[:,] 를 입력
# Name, Age만 선택하고 Job Column은 필요없다면?
# df.iloc[x:y] 에서 x는 row의 조건을, y는 column의 조건을 지정해주는 부분임.

df.iloc[:,0:2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
    </tr>
  </tbody>
</table>
</div>




```python
# row와 column 모두 2개씩만 선택하려고 한다면?

df.iloc[0:2, 0:2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
    </tr>
  </tbody>
</table>
</div>



### Filter by Column Name


```python
df = pd.read_csv('data/friend_list_no_head.csv', header = None, names = ['name', 'age', 'job'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# job이라는 정보는 필요없다면?

df_filtered = df[['name', 'age']]
```


```python
df_filtered
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
    </tr>
  </tbody>
</table>
</div>




```python
# filter 함수를 활용하여 특정 column만 선택 가능

df.filter(items = ['age', 'job'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>30</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>40</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>45</td>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>25</td>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>




```python
# column name에 a가 들어있는 column만 선택하려면?

df.filter(like = 'a', axis = 1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Julia</td>
      <td>40</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>45</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chris</td>
      <td>25</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 정규표현식(Regex)도 사용 가능!
# 예시: column name이 b로 끝나는 column만 선택하고 싶다면?

df.filter(regex = 'b$', axis = 1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>manager</td>
    </tr>
    <tr>
      <th>5</th>
      <td>intern</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 6강 : Drop row or column (행/열 삭제)

### Drop rows by index name


```python
import pandas as pd

# index가 name인 데이터프레임을 생성

friends = [{'age': 15, 'job': 'student'},
          {'age': 25, 'job': 'developer'},
          {'age': 30, 'job': 'teacher'}]

df = pd.DataFrame(friends,
                  index = ['John', 'Jenny', 'Nate'],
                  columns = ['age', 'job'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>John</th>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>Jenny</th>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>Nate</th>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# John과 Nate의 정보를 제외하고 나머지를 선택하려면?

df.drop(['John', 'Nate'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Jenny</th>
      <td>25</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 주의: 상기 명령어는 원래의 데이터프레임에 아무런 변동을 만들지 않음.

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>John</th>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>Jenny</th>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>Nate</th>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터프레임에서 John과 Nate의 정보를 삭제하고 나머지만 남겨두려면? (1/2)

df = df.drop(['John', 'Nate'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Jenny</th>
      <td>25</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터프레임을 원복하고...

df = pd.DataFrame(friends,
                  index = ['John', 'Jenny', 'Nate'],
                  columns = ['age', 'job'])

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>John</th>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>Jenny</th>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>Nate</th>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터프레임에서 John과 Nate의 정보를 삭제하고 나머지만 남겨두려면? (2/2)
# 별도의 assign 절차 ('df =' 부분에 해당) 가 필요하지 않음

df.drop(['John', 'Nate'], inplace = True)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Jenny</th>
      <td>25</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>



### Drop rows by index number


```python
# 새로운 데이터 생성 : index는 숫자이고, name은 column 중에 하나인 데이터프레임

friends = [{'name': 'John', 'age': 15, 'job': 'student'},
          {'name': 'Ben', 'age': 25, 'job': 'developer'},
          {'name': 'Jenny', 'age': 30, 'job': 'teacher'}]

df = pd.DataFrame(friends,
                  columns = ['name', 'age', 'job'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# John과 Jenny의 정보를 삭제하려면?

df = df.drop(df.index[[0,2]])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>25</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>



### Drop rows by value of column


```python
# 데이터프레임을 다시 복원

df = pd.DataFrame(friends,
                  columns = ['name', 'age', 'job'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 특정 조건의 정보를 선택하려면?
# 예시: 나이가 20세 이상인 정보만 선택하고 싶다면?

df = df[df.age > 20]
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>



### Drop columns


```python
# 데이터프레임을 다시 복원

df = pd.DataFrame(friends,
                  columns = ['name', 'age', 'job'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 예시: age라는 column을 삭제하려면? (1/2)
# 'axis = 1'은 '칼럼 중에서'를 의미함.

df = df.drop('age', axis = 1)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 데이터프레임을 다시 복원

df = pd.DataFrame(friends,
                  columns = ['name', 'age', 'job'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>25</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 예시: age라는 column을 삭제하려면? (2/2)
# 별도의 assign 절차 ('df =' 부분에 해당) 가 필요하지 않음

df.drop('age', axis = 1, inplace = True)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ben</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jenny</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 7강 : row, column create/update (행/열 생성 및 수정)

### Create/Update a column


```python
import pandas as pd
```


```python
# 데이터프레임을 생성

friend_dict_list = [{'name': 'Jone', 'age': 15, 'job': 'student'},
                   {'name': 'Jenny', 'age': 30, 'job': 'developer'},
                   {'name': 'Nate', 'age': 30, 'job': 'teacher'}]
df = pd.DataFrame(friend_dict_list, columns = ['name', 'age', 'job'])
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>15</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# salary 라는 새로운 열을 생성하려면?

df['salary'] = 0
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
      <th>salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>15</td>
      <td>student</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 직업이 학생이라면 연봉이 없고, 학생이 아니라면 연봉이 있도록 데이터를 고치려면?

import numpy as np

df['salary'] = np.where(df['job'] != 'student', 'yes', 'no')
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>job</th>
      <th>salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>15</td>
      <td>student</td>
      <td>no</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>30</td>
      <td>developer</td>
      <td>yes</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>teacher</td>
      <td>yes</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 새로운 예제 데이터프레임을 생성

friend_dict_list = [{'name': 'Jone', 'midterm': 95, 'final': 85},
                   {'name': 'Jenny', 'midterm': 85, 'final': 80},
                   {'name': 'Nate', 'midterm': 30, 'final': 10}]
df = pd.DataFrame(friend_dict_list, columns = ['name', 'midterm', 'final'])
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 중간고사와 기말고사의 합산 점수를 'total'이라는 칼럼으로 새로 추가하려면?

df['total'] = df['midterm'] + df['final']
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
      <th>total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
      <td>180</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
      <td>165</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 평균점수도 추가해보면?

df['average'] = df['total'] / 2
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
      <th>total</th>
      <th>average</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
      <td>180</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
      <td>165</td>
      <td>82.5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
      <td>40</td>
      <td>20.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 리스트를 사용해서 성적(grade)을 매긴다면?

# 우선 성적을 저장할 리스트를 하나 만들고,
grades = []

# 평균점수를 인자로 받아서 성적을 매기는 for문을 돌린 다음에,
for row in df['average']:
    if row >= 90:
        grades.append('A')
    elif row >= 80:
        grades.append('B')
    else:
        grades.append('F')

# 성적을 저장한 리스트(grades)를 데이터프레임의 새로운 칼럼으로 추가함        
df['grade'] = grades
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
      <th>total</th>
      <th>average</th>
      <th>grade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
      <td>180</td>
      <td>90.0</td>
      <td>A</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
      <td>165</td>
      <td>82.5</td>
      <td>B</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
      <td>40</td>
      <td>20.0</td>
      <td>F</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 성적(grade)을 Pass/Fail 기준으로 변경. F = Fail, 나머지는 Pass.
# Pandas의 apply 함수를 사용하기 위해서 우선 인자가 될 함수를 정의함

def pass_or_fail(row):
    if row != 'F':
        return "Pass"
    else:
        return "Fail"
```


```python
# 위에서 정의한 pass_or_fail 함수를 인자로 받는 apply 함수를 적용

df.grade = df.grade.apply(pass_or_fail)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
      <th>total</th>
      <th>average</th>
      <th>grade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
      <td>180</td>
      <td>90.0</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
      <td>165</td>
      <td>82.5</td>
      <td>Pass</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
      <td>40</td>
      <td>20.0</td>
      <td>Fail</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Feature Engineering에서 Feature Extraction에 해당하는 부분을 맛보기로 해보자.
# 일단 실습용 데이터프레임을 만들고...

date_list = [
    {
        'yyyy-mm-dd' : '2000-06-27'
    },
    {
        'yyyy-mm-dd' : '2007-10-27'
    }    
]

df = pd.DataFrame(date_list, columns = ['yyyy-mm-dd'])
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2007-10-27</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 여기서 연도만 따로 빼려면?

# row를 받아서 dash('-')를 기준으로 문자열을 나눈 다음, 첫번째 요소('[0]')만 선택
def extract_year(row):
    return row.split('-')[0]
```


```python
# 위에서 정의한 extract_year 함수를 적용하는 apply 함수를 사용

df['year'] = df['yyyy-mm-dd'].apply(extract_year)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
      <td>2000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2007-10-27</td>
      <td>2007</td>
    </tr>
  </tbody>
</table>
</div>



### Create/Update a row


```python
# 새로운 예제 데이터프레임을 생성

friend_dict_list = [{'name': 'Jone', 'midterm': 95, 'final': 85},
                   {'name': 'Jenny', 'midterm': 85, 'final': 80},
                   {'name': 'Nate', 'midterm': 30, 'final': 10}]
df = pd.DataFrame(friend_dict_list, columns = ['name', 'midterm', 'final'])
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Ben의 성적을 추가하려면?

# 우선 Ben의 성적을 df2라는 새로운 데이터프레임에 담는다.
# df와 df2를 합칠 예정이기 때문에 df2에도 column name option을 지정해줘야 함.

df2 = pd.DataFrame([
    ['Ben', 50, 50]
], columns = ['name', 'midterm', 'final'])
```


```python
df2.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ben</td>
      <td>50</td>
      <td>50</td>
    </tr>
  </tbody>
</table>
</div>




```python
# df와 df2를 합친다.
# 'ignore_index = True' : 데이터프레임을 합칠 때에 df2의 index 값은 무시하는 option

df.append(df2, ignore_index = True)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>midterm</th>
      <th>final</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jone</td>
      <td>95</td>
      <td>85</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jenny</td>
      <td>85</td>
      <td>80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nate</td>
      <td>30</td>
      <td>10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ben</td>
      <td>50</td>
      <td>50</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 8강 : Group by (데이터 그룹 만들기)


```python
# 예시 데이터프레임을 만들고...

import pandas as pd

student_list = [{'name': 'John', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Nate', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Abraham', 'major': "Physics", 'sex': "male"},
                {'name': 'Brian', 'major': "Psychology", 'sex': "male"},
                {'name': 'Janny', 'major': "Economics", 'sex': "female"},
                {'name': 'Yuna', 'major': "Economics", 'sex': "female"},
                {'name': 'Jeniffer', 'major': "Computer Science", 'sex': "female"},
                {'name': 'Edward', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Zara', 'major': "Psychology", 'sex': "female"},
                {'name': 'Wendy', 'major': "Economics", 'sex': "female"},
                {'name': 'Sera', 'major': "Psychology", 'sex': "female"}
         ]
df = pd.DataFrame(student_list, columns = ['name', 'major', 'sex'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>major</th>
      <th>sex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham</td>
      <td>Physics</td>
      <td>male</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Brian</td>
      <td>Psychology</td>
      <td>male</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Janny</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Yuna</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jeniffer</td>
      <td>Computer Science</td>
      <td>female</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Edward</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Zara</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Wendy</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Sera</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 각 학과별로 몇명이 있는지를 확인하려면?
# groupby_major라는 변수를 만들어서 groupby 함수를 적용

groupby_major = df.groupby('major')
```


```python
groupby_major.groups
```




    {'Computer Science': Int64Index([0, 1, 6, 7], dtype='int64'),
     'Economics': Int64Index([4, 5, 9], dtype='int64'),
     'Physics': Int64Index([2], dtype='int64'),
     'Psychology': Int64Index([3, 8, 10], dtype='int64')}




```python
# groupby_major 변수의 정보를 시각적으로 좀 더 잘보이게 확인해보자
# print(name + " : " + str(len(group))) : 우선 학과명과 인원이 출력되게 한 후,
# print(group) : 학과별로 소속 학생의 상세 정보를 보여주고
# print() : 학과 사이에는 빈 줄을 하나씩 넣어줌

for name, group in groupby_major:
    print(name + " : " + str(len(group)))
    print(group)
    print()
```

    Computer Science : 4
           name             major     sex
    0      John  Computer Science    male
    1      Nate  Computer Science    male
    6  Jeniffer  Computer Science  female
    7    Edward  Computer Science    male

    Economics : 3
        name      major     sex
    4  Janny  Economics  female
    5   Yuna  Economics  female
    9  Wendy  Economics  female

    Physics : 1
          name    major   sex
    2  Abraham  Physics  male

    Psychology : 3
         name       major     sex
    3   Brian  Psychology    male
    8    Zara  Psychology  female
    10   Sera  Psychology  female




```python
# 각 학과별로 몇명이 있는지를 데이터프레임으로 만들어보자.
# reset_index() : 'major'라는 칼럼 이름이 column으로 들어오게 재정렬해줌

df_major_cnt = pd.DataFrame( {'count' : groupby_major.size()} ).reset_index()
df_major_cnt
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>major</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Computer Science</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Economics</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Physics</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Psychology</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 성별로 학생들을 분류해보면?

groupby_sex = df.groupby('sex')
```


```python
for name, group in groupby_sex:
    print(name + " : " + str(len(group)))
    print(group)
    print()
```

    female : 6
            name             major     sex
    4      Janny         Economics  female
    5       Yuna         Economics  female
    6   Jeniffer  Computer Science  female
    8       Zara        Psychology  female
    9      Wendy         Economics  female
    10      Sera        Psychology  female

    male : 5
          name             major   sex
    0     John  Computer Science  male
    1     Nate  Computer Science  male
    2  Abraham           Physics  male
    3    Brian        Psychology  male
    7   Edward  Computer Science  male


<br>
### 9강 : Drop duplicate (중복 데이터 삭제)

### How to remove duplicate row in dataframe


```python
import pandas as pd

student_list = [{'name': 'John', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Nate', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Abraham', 'major': "Physics", 'sex': "male"},
                {'name': 'Brian', 'major': "Psychology", 'sex': "male"},
                {'name': 'Janny', 'major': "Economics", 'sex': "female"},
                {'name': 'Yuna', 'major': "Economics", 'sex': "female"},
                {'name': 'Jeniffer', 'major': "Computer Science", 'sex': "female"},
                {'name': 'Edward', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Zara', 'major': "Psychology", 'sex': "female"},
                {'name': 'Wendy', 'major': "Economics", 'sex': "female"},
                {'name': 'Sera', 'major': "Psychology", 'sex': "female"},
                {'name': 'John', 'major': "Computer Science", 'sex': "male"},
         ]
df = pd.DataFrame(student_list, columns = ['name', 'major', 'sex'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>major</th>
      <th>sex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham</td>
      <td>Physics</td>
      <td>male</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Brian</td>
      <td>Psychology</td>
      <td>male</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Janny</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Yuna</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jeniffer</td>
      <td>Computer Science</td>
      <td>female</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Edward</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Zara</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Wendy</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Sera</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
    <tr>
      <th>11</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 중복된 행을 확인하려면? duplicated 함수의 결과값이 True인 항목을 확인하자.

df.duplicated()
```




    0     False
    1     False
    2     False
    3     False
    4     False
    5     False
    6     False
    7     False
    8     False
    9     False
    10    False
    11     True
    dtype: bool




```python
# 중복된 행을 제거하려면?

df.drop_duplicates()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>major</th>
      <th>sex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham</td>
      <td>Physics</td>
      <td>male</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Brian</td>
      <td>Psychology</td>
      <td>male</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Janny</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Yuna</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jeniffer</td>
      <td>Computer Science</td>
      <td>female</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Edward</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Zara</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Wendy</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Sera</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
  </tbody>
</table>
</div>



### How to remove duplicate by column value


```python
student_list = [{'name': 'John', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Nate', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Abraham', 'major': "Physics", 'sex': "male"},
                {'name': 'Brian', 'major': "Psychology", 'sex': "male"},
                {'name': 'Janny', 'major': "Economics", 'sex': "female"},
                {'name': 'Yuna', 'major': "Economics", 'sex': "female"},
                {'name': 'Jeniffer', 'major': "Computer Science", 'sex': "female"},
                {'name': 'Edward', 'major': "Computer Science", 'sex': "male"},
                {'name': 'Zara', 'major': "Psychology", 'sex': "female"},
                {'name': 'Wendy', 'major': "Economics", 'sex': "female"},
                {'name': 'Nate', 'major': None, 'sex': "male"},
                {'name': 'John', 'major': "Computer Science", 'sex': None},
         ]
df = pd.DataFrame(student_list, columns = ['name', 'major', 'sex'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>major</th>
      <th>sex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham</td>
      <td>Physics</td>
      <td>male</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Brian</td>
      <td>Psychology</td>
      <td>male</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Janny</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Yuna</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jeniffer</td>
      <td>Computer Science</td>
      <td>female</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Edward</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Zara</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Wendy</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Nate</td>
      <td>None</td>
      <td>male</td>
    </tr>
    <tr>
      <th>11</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 이름(name)을 기준으로 중복 여부를 판단하려면?
# 본 예시에서 John과 Nate는 중복된 이름이나,
# major/sex 정보는 항목별로 조금씩 다르기 때문에 duplicate 함수로 걸러낼 수 없음.
# 이러한 경우, duplicate를 판단하는 기준이 무엇인지를 option으로 지정해야 함.

df.duplicated(['name'])
```




    0     False
    1     False
    2     False
    3     False
    4     False
    5     False
    6     False
    7     False
    8     False
    9     False
    10     True
    11     True
    dtype: bool




```python
# 이름(name)을 기준으로 중복인 행은 제거하려면?
# keep = 'first' : 중복인 여러 개의 행 중, 첫 번째 행을 남겨두고 나머지를 삭제함.
# keep = 'last' : 중복인 여러 개의 행 중, 마지막 행을 남겨두고 나머지를 삭제함.
# default option은 keep = 'first'임.

df.drop_duplicates(['name'], keep = 'first')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>major</th>
      <th>sex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham</td>
      <td>Physics</td>
      <td>male</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Brian</td>
      <td>Psychology</td>
      <td>male</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Janny</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Yuna</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jeniffer</td>
      <td>Computer Science</td>
      <td>female</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Edward</td>
      <td>Computer Science</td>
      <td>male</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Zara</td>
      <td>Psychology</td>
      <td>female</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Wendy</td>
      <td>Economics</td>
      <td>female</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 10강 : NaN (None) 찾아서 다른 값으로 변경하기 (fillna)


```python
import pandas as pd

school_id_list = [{'name': 'John', 'job': "teacher", 'age': 40},
                {'name': 'Nate', 'job': "teacher", 'age': 35},
                {'name': 'Yuna', 'job': "teacher", 'age': 37},
                {'name': 'Abraham', 'job': "student", 'age': 10},
                {'name': 'Brian', 'job': "student", 'age': 12},
                {'name': 'Janny', 'job': "student", 'age': 11},
                {'name': 'Nate', 'job': "teacher", 'age': None},
                {'name': 'John', 'job': "student", 'age': None}
         ]
df = pd.DataFrame(school_id_list, columns = ['name', 'job', 'age'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Yuna</td>
      <td>teacher</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham</td>
      <td>student</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>student</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Janny</td>
      <td>student</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>John</td>
      <td>student</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.shape
```




    (8, 3)




```python
# NaN (None) 값을 찾아내려면? (1/3)
# name과 job 칼럼은 8개가 NaN이 아닌 반면에, age는 6개만 NaN이 아님.
# 즉, age의 2개는 NaN에 해당함.

df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 8 entries, 0 to 7
    Data columns (total 3 columns):
    name    8 non-null object
    job     8 non-null object
    age     6 non-null float64
    dtypes: float64(1), object(2)
    memory usage: 272.0+ bytes



```python
# NaN (None) 값을 찾아내려면? (2/3)
# 결과값이 True로 출력되는 부분이 NaN 값임.

df.isna()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>5</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>6</th>
      <td>False</td>
      <td>False</td>
      <td>True</td>
    </tr>
    <tr>
      <th>7</th>
      <td>False</td>
      <td>False</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
# NaN (None) 값을 찾아내려면? (3/3)
# 결과값이 True로 출력되는 부분이 NaN 값임.

df.isnull()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>5</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>6</th>
      <td>False</td>
      <td>False</td>
      <td>True</td>
    </tr>
    <tr>
      <th>7</th>
      <td>False</td>
      <td>False</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
# NaN (None) 값을 찾아서 0으로 변경하려면?

df.age = df.age.fillna(0)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Yuna</td>
      <td>teacher</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham</td>
      <td>student</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>student</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Janny</td>
      <td>student</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>John</td>
      <td>student</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 일단 데이터프레임을 복구하고...

school_id_list = [{'name': 'John', 'job': "teacher", 'age': 40},
                {'name': 'Nate', 'job': "teacher", 'age': 35},
                {'name': 'Yuna', 'job': "teacher", 'age': 37},
                {'name': 'Abraham', 'job': "student", 'age': 10},
                {'name': 'Brian', 'job': "student", 'age': 12},
                {'name': 'Janny', 'job': "student", 'age': 11},
                {'name': 'Nate', 'job': "teacher", 'age': None},
                {'name': 'John', 'job': "student", 'age': None}
         ]
df = pd.DataFrame(school_id_list, columns = ['name', 'job', 'age'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Yuna</td>
      <td>teacher</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham</td>
      <td>student</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>student</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Janny</td>
      <td>student</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>John</td>
      <td>student</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# NaN (None) 값을 0으로 변경했더니, 선생님도 학생도 0세가 되어버린다.
# 좀 더 그럴싸한 값은 없을까?
# 이를테면, NaN (None) 값을 찾아서 중앙값(medium)으로 변경하려면?
# 예시: Nate의 age는 선생님들의 중앙값으로, John의 age는 학생들의 중앙값으로 변경

df['age'].fillna(df.groupby('job')['age'].transform('median'), inplace = True)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Yuna</td>
      <td>teacher</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham</td>
      <td>student</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>student</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Janny</td>
      <td>student</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Nate</td>
      <td>teacher</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>John</td>
      <td>student</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 11강 : apply 함수, 다양한 예제로 활용해보기


```python
import pandas as pd

date_list = [{'yyyy-mm-dd': '2000-06-27'},
             {'yyyy-mm-dd': '2002-09-24'},
             {'yyyy-mm-dd': '2005-12-20'}]
df = pd.DataFrame(date_list, columns = ['yyyy-mm-dd'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
    </tr>
  </tbody>
</table>
</div>




```python
# apply 함수를 이용하여 year 칼럼 추가하기

def extract_year(column):
    return column.split("-")[0]

df['year'] = df['yyyy-mm-dd'].apply(extract_year)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
      <td>2000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
      <td>2002</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
      <td>2005</td>
    </tr>
  </tbody>
</table>
</div>




```python
# age 칼럼 추가하기 : apply 함수는 parameter를 어떻게 전달하고 받는가?
# age = 올해 연도(2018년) - year로 가정함.
# 올해 연도(2018년)는 parameter로 전달해줘야 함.

def get_age(year, current_year):
    return current_year - int(year)

df['age'] = df['year'].apply(get_age, current_year=2018)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
      <th>year</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
      <td>2000</td>
      <td>18</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
      <td>2002</td>
      <td>16</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
      <td>2005</td>
      <td>13</td>
    </tr>
  </tbody>
</table>
</div>




```python
# introduce 칼럼 추가하기 : apply 함수에서 parameter는 여러 개를 쓸 수 있을까?
# 가능하다. parameter마다 값 전달해주는 것을 누락하지만 않는다면.

def get_introduce(age, prefix, suffix):
    return prefix + str(age) + suffix

df['introduce'] = df['age'].apply(get_introduce, prefix = "I am ", suffix = " years old")
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
      <th>year</th>
      <th>age</th>
      <th>introduce</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
      <td>2000</td>
      <td>18</td>
      <td>I am 18 years old</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
      <td>2002</td>
      <td>16</td>
      <td>I am 16 years old</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
      <td>2005</td>
      <td>13</td>
      <td>I am 13 years old</td>
    </tr>
  </tbody>
</table>
</div>




```python
# introduce 칼럼 추가하기 2 : 여러 개의 column에 apply 함수를 적용할 수 있을까?

# 우선 함수를 만들어 준 후에,

def get_introduce_2(row):
    return "I was born in " + str(row.year) + " my age is " + str(row.age)

# 새로 만든 함수를 apply에 적용시킨다.
# year와 age라는 column을 불러와야 하기 때문에 axis = 1 이라는 option을 사용한다.
# 참고 : df['introduce'] 와 df.introduce 는 동일한 결과를 만들어낸다.

df.introduce = df.apply(get_introduce_2, axis = 1)
df['introduce_2'] = df.apply(get_introduce_2, axis = 1)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>yyyy-mm-dd</th>
      <th>year</th>
      <th>age</th>
      <th>introduce</th>
      <th>introduce_2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
      <td>2000</td>
      <td>18</td>
      <td>I was born in 2000 my age is 18</td>
      <td>I was born in 2000 my age is 18</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
      <td>2002</td>
      <td>16</td>
      <td>I was born in 2002 my age is 16</td>
      <td>I was born in 2002 my age is 16</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
      <td>2005</td>
      <td>13</td>
      <td>I was born in 2005 my age is 13</td>
      <td>I was born in 2005 my age is 13</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 12강 : map, applymap 함수 활용

### map 함수의 활용


```python
import pandas as pd

date_list = [{'date': '2000-06-27'},
            {'date': '2002-09-24'},
            {'date': '2005-12-20'}]
df = pd.DataFrame(date_list, columns = ['date'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 연도만 뽑아내서 year라는 칼럼을 만들어보자.
# apply 함수와 사용법은 동일한 map이라는 함수를 사용할 수 있음.

def extract_year(date):
    return date.split('-')[0]

df['year'] = df['date'].map(extract_year)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000-06-27</td>
      <td>2000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2002-09-24</td>
      <td>2002</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2005-12-20</td>
      <td>2005</td>
    </tr>
  </tbody>
</table>
</div>




```python
# map 함수의 다른 사용 예제
# 머신러닝을 하다보면, Category에 대해 문자 분류를 숫자로 바꿔줘야 할 때가 종종 있다.
# 그럴 때에 map 함수가 유용하게 사용된다.
# map 함수 기능: apply처럼 칼럼 변경 + dictionary를 직접 전달해서 원하는 값으로 변경

job_list = [{'age': 20, 'job': 'student'},
           {'age': 30, 'job': 'developer'},
           {'age': 30, 'job': 'teacher'}]
df = pd.DataFrame(job_list)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20</td>
      <td>student</td>
    </tr>
    <tr>
      <th>1</th>
      <td>30</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>30</td>
      <td>teacher</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 학생은 1, 개발자는 2, 선생님은 3으로 job 칼럼을 바꿔주려면?

df.job = df.job.map({'student': 1, 'developer': 2, 'teacher': 3})
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>30</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>30</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>



### applymap 함수의 활용


```python
# 1개의 칼럼이 아니라 모든 칼럼에 변경 사항을 적용하고 싶을 때 applymap을 사용

x_y = [{'x': 5.5, 'y': -5.6, 'z': -1.1},
      {'x': -5.2, 'y': 5.5, 'z': -2.2},
      {'x': -1.6, 'y': -4.5, 'z': -3.3}]
df = pd.DataFrame(x_y)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>x</th>
      <th>y</th>
      <th>z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.5</td>
      <td>-5.6</td>
      <td>-1.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.2</td>
      <td>5.5</td>
      <td>-2.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-1.6</td>
      <td>-4.5</td>
      <td>-3.3</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 예시: 상기 데이터프레임 전체 값에 대해 반올림 처리하려면?

import numpy as np

df = df.applymap(np.around)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>x</th>
      <th>y</th>
      <th>z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>6.0</td>
      <td>-6.0</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.0</td>
      <td>6.0</td>
      <td>-2.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-2.0</td>
      <td>-4.0</td>
      <td>-3.0</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### 13강 : 칼럼 내 유니크한 값 뽑기, 갯수 확인 (unique, value_counts)


```python
import pandas as pd

job_list = [{'name': 'John', 'job': "teacher"},
                {'name': 'Nate', 'job': "teacher"},
                {'name': 'Fred', 'job': "teacher"},
                {'name': 'Abraham', 'job': "student"},
                {'name': 'Brian', 'job': "student"},
                {'name': 'Janny', 'job': "developer"},
                {'name': 'Nate', 'job': "teacher"},
                {'name': 'Obrian', 'job': "dentist"},
                {'name': 'Yuna', 'job': "teacher"},
                {'name': 'Rob', 'job': "lawyer"},
                {'name': 'Brian', 'job': "student"},
                {'name': 'Matt', 'job': "student"},
                {'name': 'Wendy', 'job': "banker"},
                {'name': 'Edward', 'job': "teacher"},
                {'name': 'Ian', 'job': "teacher"},
                {'name': 'Chris', 'job': "banker"},
                {'name': 'Philip', 'job': "lawyer"},
                {'name': 'Janny', 'job': "basketball player"},
                {'name': 'Gwen', 'job': "teacher"},
                {'name': 'Jessy', 'job': "student"}
         ]
df = pd.DataFrame(job_list, columns = ['name', 'job'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Fred</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham</td>
      <td>student</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brian</td>
      <td>student</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Janny</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Nate</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Obrian</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Yuna</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Rob</td>
      <td>lawyer</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Brian</td>
      <td>student</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Matt</td>
      <td>student</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Wendy</td>
      <td>banker</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Edward</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Ian</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Chris</td>
      <td>banker</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Philip</td>
      <td>lawyer</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Janny</td>
      <td>basketball player</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Gwen</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Jessy</td>
      <td>student</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 칼럼 내에서 유니크한 값만 뽑아내고 싶을 때 unique 함수 사용

df.job.unique()
```




    array(['teacher', 'student', 'developer', 'dentist', 'lawyer', 'banker',
           'basketball player'], dtype=object)




```python
# 각 직업 별로 몇 개의 데이터가 있는지 확인하려면 value_counts 함수 사용

df.job.value_counts()
```




    teacher              8
    student              5
    banker               2
    lawyer               2
    developer            1
    basketball player    1
    dentist              1
    Name: job, dtype: int64


<br>
### 14강 : 데이터프레임 합치기 (concat, append)

### 행(row)으로 합치기


```python
import pandas as pd

l1 = [{'name': 'John', 'job': "teacher"},
      {'name': 'Nate', 'job': "student"},
      {'name': 'Fred', 'job': "developer"}]

l2 = [{'name': 'Ed', 'job': "dentist"},
      {'name': 'Jack', 'job': "farmer"},
      {'name': 'Ted', 'job': "designer"}]

df1 = pd.DataFrame(l1, columns = ['name', 'job'])
df2 = pd.DataFrame(l2, columns = ['name', 'job'])
```


```python
df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>student</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Fred</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ed</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jack</td>
      <td>farmer</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ted</td>
      <td>designer</td>
    </tr>
  </tbody>
</table>
</div>




```python
# column name이 같은 2개의 데이터프레임을 합치려면? (1/2)
# 방법 1 : concat 함수 사용

result = pd.concat([df1, df2], ignore_index = True)
result
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>student</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Fred</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ed</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jack</td>
      <td>farmer</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Ted</td>
      <td>designer</td>
    </tr>
  </tbody>
</table>
</div>




```python
# column name이 같은 2개의 데이터프레임을 합치려면? (2/2)
# 방법 2 : append 함수 사용

result = df1.append(df2, ignore_index = True)
result
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>teacher</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>student</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Fred</td>
      <td>developer</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ed</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jack</td>
      <td>farmer</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Ted</td>
      <td>designer</td>
    </tr>
  </tbody>
</table>
</div>



### 열(column)로 합치기


```python
l3 = [{'name': 'John', 'job': 'dentist'},
     {'name': 'Nate', 'job': 'student'},
     {'name': 'Jack', 'job': 'developer'}]

l4 = [{'age': 25, 'country': 'U.S'},
     {'age': 30, 'country': 'U.K'},
     {'age': 45, 'country': 'Korea'}]

df1 = pd.DataFrame(l3, columns = ['name', 'job'])
df2 = pd.DataFrame(l4, columns = ['age', 'country'])
```


```python
df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>job</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>dentist</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>student</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jack</td>
      <td>developer</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>U.S</td>
    </tr>
    <tr>
      <th>1</th>
      <td>30</td>
      <td>U.K</td>
    </tr>
    <tr>
      <th>2</th>
      <td>45</td>
      <td>Korea</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 2개의 데이터프레임을 합치려면? concat 함수 사용!
# 열(column)로 합치는 것이기 때문에 axis = 1 이라는 option을 추가해야함

result = pd.concat([df1, df2], axis = 1, ignore_index = True)
result
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>dentist</td>
      <td>25</td>
      <td>U.S</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nate</td>
      <td>student</td>
      <td>30</td>
      <td>U.K</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jack</td>
      <td>developer</td>
      <td>45</td>
      <td>Korea</td>
    </tr>
  </tbody>
</table>
</div>


<br>
### Bouns Track : (데이터프레임이 아니라) 리스트를 합치는 방법


```python
# 머신러닝에서 실제값과 예측값을 비교할 때,
# 리스트 형식으로 보면 어떤 값이 제대로 예측되는지 분간하기가 어려운 경우가 있음.
# 이런 경우, 데이터프레임으로 만들어서 보면 분간하기가 좀 더 쉬워짐

label = [1, 2, 3, 4, 5]
prediction = [1, 2, 2, 4, 4]
```


```python
comparison = pd.DataFrame({'label': label, 'prediction': prediction})
comparison
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>label</th>
      <th>prediction</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>
<br>
