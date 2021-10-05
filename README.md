# 211001_sorting_001

sorting에 대표적인 정렬 알고리즘인 선택 정렬, 삽입 정렬, 퀵 정렬, 계수 정렬을 알아보자



## 선택 정렬

가장 작은 데이터를 선택해 맨 앞에 있는 데이터와 위치를 바꾸고 다음 낮은 숫자를 선택하여 위치를 바꾼다

### example
array_ = [7,5,9,0,3,1,6,2,4,8]

for i in range(len(array_)):

  idx = array_.index(min(array_[i:]))
  
  min_v = min(array_[i:])

  array_[idx] = array_[i]
  
  array_[i] = min_v


print(array_)

## 삽입 정렬

데이터를 하나씩 확인하며, 각 데이터를 적절한 위치에 삽입

swap하여 데이터를 정렬함

### example

array_ = [7,5,9,0,3,1,6,2,4,8]

for i in range(1, len(array_)):

  for ii in range(i, 0 ,-1):
  
    if array_[ii] < array_[ii-1]:
    
      array_[ii], array_[ii-1] = array_[ii-1], array_[ii]
    
    else:
    
      break

print(array_)


## 퀵 정렬


### example
array_ = [7,5,9,0,3,1,6,2,4,8]

def quick_sort(arr):

  if len(arr) <= 1:
  
    return arr

  pivot = arr[0]
  
  tail = arr[1:]

  left_side = [x for x in tail if x <= pivot]
  
  right_side = [x for x in tail if x > pivot]

  print("left_side :" , left_side)
  
  print("right_side :" , right_side)
  
  return quick_sort(left_side) + [pivot] + quick_sort(right_side)


print(quick_sort(array_))


![image](https://user-images.githubusercontent.com/88085974/135959452-5298de40-9c5e-4e19-9ba4-98cae1e2cdf0.png)



## 계수 정렬

특정한 조건이 부합할때만 사용할 수 있지만 매우 빠른 정렬 알고리즘

특정한 조건이란 테이터의 크기 범위가 제한되어 정수 형태로 표현할 수 있을 때만 사용

실수형 데이터는 어렵고, 가장 큰 데이터와 작은 데이터의 차이가 너무 크면 안된다.


### example
cnt = [0] * (max(array_) + 1)

for i in range(len(array_)):

  cnt[array_[i]] += 1

for i in range(len(cnt)):

  for _ in range(cnt[i]):
  
    print(i, end = '')

## 라이브러리를 활용한 정렬

key 매개변수를 입력으로 sort() 혹은 sorted()를 사용할 수 있다

### example

arr = [('x', 3), ('y', 6), ('z', 4)]

def setting(data):
  return data[1]


result = sorted(arr, key = setting)

print(result)

![image](https://user-images.githubusercontent.com/88085974/135963760-6de1586a-f22c-4de4-9950-66a4bc9ed605.png)


