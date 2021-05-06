# Sorting Algorithm

# 컴퓨터 알고리즘 4번째 과제

## 제출자 : 오성환

## 1. Sorting Algorithm이란?

## 2. Sorting Algorithm의 종류

정렬 알고리즘에는 여러 종류가 있는데, 오늘 알아볼 정렬 알고리즘은 다음 4개이다.

- 버블 정렬 (Bubble Sort)
- 선택 정렬 (Selection Sort)
- 삽입 정렬 (Insertion Sort)
- 쉘 정렬 (Shell Sort)

### 1) 버블 정렬(Bubble Sort)

**버블 정렬**은 연속된 두 개의 인덱스를 비교하여, 정한 기준의 값을 뒤로 넘겨 정렬하는 방법이다. 오름차순으로 정렬하려고 할 경우에는 비교시마다 큰 값이 뒤로 이동하여 1바퀴 돌 때 가장 큰 값이 맨 뒤에 저장되게 된다. 맨 마지막에는 비교하는 수들 중 가장 큰 값이 저장되기 때문에, (전체 배열의 크기 - 현재까지 반복된 바퀴 수)만큼 반복해주면 된다.

방법은 다음과 같다.
- 1회전
 - 첫 번째 자료와 두 번째 자료를 비교하여 교환또는 교환하지 않음, 두 번째 자료와 세 번째 자료를 비교하여 교환또는 교환하지 않음, ..., 가장 큰 자료가 맨 끝으로 이동할 때까지 비교
- n회전
 - 첫 번째 자료와 두 번째 자료를 비교하여 교환또는 교환하지 않음

### 2) 선택 정렬(Selection Sort)

**선택 정렬**은 값을 찾아 정렬하는 배열로, 현재 위치에 저장될 값의 크기가 작냐, 크냐에 따라서 **최소 선택 정렬**(Min-Selection Sort)과 **최대 선택 정렬**(Max-Selection Sort)로 구분된다. 최소 선택 정렬은 오름차순으로, 최대 선택 정렬은 내림차순으로 정렬된 것이다.

방법은 다음과 같다.
1. 가장 작은 값를 찾아서 첫 번째 값과 바꾼다.
2. 두 번째로 작은 값를 찾아서 두 번째 값과 바꾼다.
3. 세 번째로 작은 값를 찾아서 세 번째 갑과 바꾼다.
4. 배열이 정렬될 때까지 그 다음으로 작은 값을 올바른 위치로 옮기는 과정을 반복한다.

### 3) 삽입 정렬(Insertion Sort)

**삽입 정렬**은 현재 위치에서, 그 이하의 배열들을 비교하여 자신이 들어갈 위치를 찾아, 그 위치에 삽입하는 알고리즘이다. 오름차순으로 정렬하려고 할 경우에 삽입 변수가 비교 인덱스보다 클 경우 배교 인덱스 +1에 삽입 변수를 저장한다.

방법은 다음과 같다.
1. 두 번째 원소를 리스트에서 적절한 위치에 삽입한다.
2. 세 번째 원소를 리스트에서 적절한 위치에 삽입한다.
3. ...
4. 마지막 원소를 리스트에서 적절한 위치에 삽입한다.

### 4) 쉘 정렬 (Shell Sort)

**쉘 정렬**은 삽입 정렬의 성질을 이용한다. 데이터가 주어지면 데이터를 듬성듬성 나누어 삽입 정렬을 실행하고, 또 다시 나누어 삽입 정렬을 실행하면서 정렬되도록 한다.

## 2. 알고리즘의 성능 평가

그렇다면 각 정렬들의 시간복잡도를 통해 알고리즘의 성능을 평가해보자. 정렬 알고리즘의 복잡도는 다음과 같이 표로 나타낼 수 있다.

| Sorting Algorithm | 최선 | 평균 | 최악 |
|:----|:----:|:----:|----:|
| Selection Sort | O(n^2) | O(n^2) | O(n^2) |
| Bubble Sort | O(n^2) | O(n^2) | O(n^2) |
| Insertion Sort | O(n) | O(n^2) | O(n^2) |
| shell Sort | O(n) | O(n^1.5) | O(n^2) |

그래프로 보면 다음과 같다.

![제목 없음](https://user-images.githubusercontent.com/80510972/117265569-5421f500-ae8f-11eb-9b14-5eaf60e94235.png)

**선택 정렬**은 비교 횟수는 많지만 교환 횟수가 적기에 역순 정렬에서 가장 효율적이다. 하지만 비교 횟수가 많은 만큼 이미 정렬된 상태에서 자료가 추가되면 재정렬할 때 최악의 속도를 보여준다.

**버블 정렬**은 인접한 값만 계속해서 비교하는 방식으로, 최선이든 최악이든 O(n^2)의 시간복잡도를 가진다. 따라서 n값, 원수의 개수가 많아질수록 배교 횟수가 많아져 성능이 저하된다.

**삽입 정렬**은 최선의 경우 O(n)이라는 빠른 효율성을 가진다. 비교횟수를 줄이는 크기가 적은 데이터 집합을 정렬하는 알고리즘을 작성할 때 효율이 좋다. 하지만 최악의 경우에는 O(n^2)의 시간복잡도를 가지게 된다.

**쉘 정렬**은 삽입 정렬의 단점을 보완하여 성능이 삽입 정렬에 비해 우수하고, 버블 정렬의 단점 또한 보완하였다. 하지만 간격 설정에 따라 성능이 급격히 저하될 수 있다.

## 4. 자바 코드

```java
import java.util.Scanner;

public class SortingAlgorithm {
    private static Scanner scanner = new Scanner(System.in);

    static void BubbleSort(int[] list) {
        int tmp = 0;

        for(int i = list.length-1; i>0; i--) {      // i-1번째 인덱스부터 최대값으로 교환
            for(int j=0; j<=i-1; j++) {    // i-1번째 인덱스까지 비교
                if(list[j] > list[j+1]) {   // 두 값을 비교하여 크기 순이 아니라면
                    tmp = list[j];
                    list[j] = list[j+1];
                    list[j+1] = tmp;    // 두 값을 교환
                }
            }
        }   // 첫번째, 두번째만을 비교할 때까지 반복
    }

    static void SelectionSort(int[] list) {
        int Min, tmp;

        for (int i = 0; i < list.length - 1; i++) {
            Min = i;     // i번째 값을 최소값으로 놓은 후

            for (int j = i + 1; j < list.length; j++) {     // (i+1)~(size-1)번째 인덱스의 나머지 값들과 비교
                if (list[j] < list[Min]) {
                    Min = j;    // i번째 값과 비교해 더 작을 경우 최소값으로 선정
                }
            }

            tmp = list[Min];
            list[Min] = list[i];
            list[i] = tmp;      // i번째 값과 최소값을 바꿈
        }
    }

    static void InsertionSort(int[] list) {
        int tmp = 0;
        int comp = 0;

        for(int i = 1 ; i < list.length ; i++){

            tmp = list[i];   // i부터 차례로 삽입 (i는 2번째값부터)

            for(comp = i-1; comp >= 0 && list[comp] > tmp; comp--) {    // 비교값은 역순으로, i-1번째 값부터 시작
                list[comp+1] = list[comp];     // 비교값은 음수가 아니어야 하고, 비교값이 tmp 값보다 클 경우엔 한 칸 뒤로 이동
            }
            list[comp+1] = tmp;     // 빈 자리에 tmp 값을 삽입
        }   // 위 과정을 반복
    }

    static void ShellSort(int[] list) {
        int tmp = 0;

        for(int gab = list.length / 2; gab > 0; gab /= 2) {    // 간격
            for(int i = gab; i < list.length; i++) {      // i=gab 이면 나누어진 배열 중 2번째 배열에서 for 문 시작
                tmp = list[i];                    // 2번째 배열의 값부터 삽입 정렬 시작 (배열 끝까지 실행)
                int j;

                for(j = i - gab; j >= 0 && list[j] > tmp; j -= gab) {  // i-gab 을 하면 부분 배열의 n번째 값끼리 삽입 연산
                    list[j + gab] = list[j];                           // 비교해서 tmp 값보다 클 경우에 한 칸 뒤로 이동
                }
                list[j + gab] = tmp;     // 빈 자리에 tmp 값을 삽입
            }
        }
    }

    public static void main(String[] args) {

        int size = 0;

        System.out.println("어떤 종류의 정렬 알고리즘을 실행하시겠습니까?");
        System.out.println("(1)버블정렬 (2)선택정렬 (3)삽입정렬 (4)쉘정렬 (5)종료");
        System.out.print("숫자를 입력하시오 : ");

        int a = scanner.nextInt();
        if(a == 5) return;

        System.out.print("변수의 수를 입력하시오: ");
        size = scanner.nextInt();

        int[] list = new int[size];

        System.out.print("변수를 입력하시오 : ");
        for (int i=0; i<size; i++) {
            list[i] = scanner.nextInt();
        }

        if(a == 1) BubbleSort(list);
        else if(a == 2) SelectionSort(list);
        else if(a == 3) InsertionSort(list);
        else if(a == 4) ShellSort(list);

        System.out.println(" ");
        System.out.println("<정렬 완료>");
        for (int j=0; j<size; j++) {
            System.out.print(list[j] + " ");
        }
    }

}

```

## 5. 코드 결과

### 1) 버블 정렬(Bubble Sort)

![1](https://user-images.githubusercontent.com/80510972/117300947-0f10b980-aeb5-11eb-8f96-4eb67d0e556d.png)

### 2) 선택 정렬(Selection Sort)

![2](https://user-images.githubusercontent.com/80510972/117300973-189a2180-aeb5-11eb-9c39-4ebb6c20f8ea.png)

### 3) 삽입 정렬(Insertion Sort)

![3](https://user-images.githubusercontent.com/80510972/117300988-1d5ed580-aeb5-11eb-9b2f-4d17a454a5d6.png)

### 4) 쉘 정렬 (Shell Sort)

![4](https://user-images.githubusercontent.com/80510972/117301014-251e7a00-aeb5-11eb-9923-142bff821318.png)
