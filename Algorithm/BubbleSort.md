## 거품 정렬(Bubble Sort)

- 거품 정렬은 Selection Sort와 유사한 알고리즘으로 서로 인접한 두 원소의 대소를 비교하고, 조건에 맞지 않다면 자리를 교환하며 정렬하는 알고리즘이다.

- 이름의 유래로는 정렬 과정에서 원소의 이동이 거품이 수면으로 올라오는 듯한 모습을 보이기 때문에 지어졌다고 한다.

#### 정렬 방식 (오름차순)

1. 비교 및 교환: 첫 번째 회전에서 첫 번째 원소와 두 번째 원소, 두 번째 원소와 세 번째 원소, ... 이런 식으로 마지막-1 번째 원소와 마지막 원소를 비교하여 조건에 맞지 않으면 교환합니다.

2. 반복 및 제외: 첫 번째 회전이 끝나면 가장 큰 원소가 맨 뒤로 이동합니다. 두 번째 회전에서는 맨 끝에 있는 원소를 제외하고 나머지 원소를 비교합니다. 이런 식으로 정렬 회전이 진행될수록 정렬에서 제외되는 데이터가 하나씩 늘어납니다.

<img src='./Assets/bubblesort.GIF'>

### Python

```
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(1, n - i):
            if arr[j - 1] > arr[j]:
                arr[j - 1], arr[j] = arr[j], arr[j - 1]
    return arr

# 예제 사용
arr = [64, 34, 25, 12, 22, 11, 90]
sorted_arr = bubble_sort(arr)
print("Sorted array is:", sorted_arr)

```

1. for i in range(n): 제외될 원소의 갯수를 의미합니다. 1회전이 끝난 후 배열의 마지막 위치에는 가장 큰 원소가 위치하기 때문에 하나씩 증가시켜줍니다.
2. for j in range(1, n - i): 원소를 비교할 인덱스를 뽑을 반복문입니다. j는 현재 원소를 가리키고, j-1은 이전 원소를 가리키므로 j는 1부터 시작합니다.
3. if arr[j - 1] > arr[j]: 현재 가리키는 두 원소를 비교합니다. 오름차순 정렬에서는 현재 원소보다 이전 원소가 더 크다면 서로 자리를 교환합니다.

## 시간 복잡도

- 시간 복잡도를 계산하면, (n-1) + (n-2) + (n-3) + ... + 2 + 1 => n(n-1)/2이므로 O(n^2) 입니다. Bubble Sort는 정렬 상태와 관계없이 2개의 원소를 비교하므로 최선, 평균, 최악의 경우 모두 시간 복잡도가 O(n^2) 으로 동일합니다.

### 장점

- 구현이 매우 간단하고, 소스코드가 직관적입니다.
- 정렬하고자 하는 배열 안에서 교환하는 방식이므로 다른 메모리 공간을 필요로 하지 않습니다. => 제자리 정렬(in-place sorting)

### 단점

- 시간 복잡도가 최악, 최선, 평균 모두 O(n^2) 으로 매우 비효율적입니다.
- 정렬되지 않은 원소가 정렬된 자리로 이동하기 위해 교환 연산(swap)이 많이 일어납니다.
