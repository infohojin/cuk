---
layout: java
---
## 03강.JAVA-배열

### 배열이 필요한 이유
여러 개의 변수 선언.

각각의 독립적인 변수를 선언시 메모리의 자원이 순차적으로 배치가 되지 않는다.

#### 유사한 변수
배열을 사용하기 위해서는 하나로 묶고자 하는 변수의 타입이 유사해야 한다.

Int s0, s1, s2, s3, s5, s6, s7;
유사한 이름을 가지고 있음. 그리고 동일한 데이터 타입을 가지고 있음.


#### 선언방법
1) 자바에서 배열의 선언방법
```
Int[] s;
```
변수의 타입형 뒤에 []를 붙여서 선언을 합니다.

S = new int[10];


퀴즈)
자바에서 다음과 같이 배열을 작성한 경우 할당되는 메모리의 크기는?

s = new int[5];

해설> 자바의 경우 int형 자료는 4바이트의 크기를 가집니다. 그리고 5개의 요소를 가지는 배열을 선언하기 땨문에
4 * 5 = 20 바이트가 할당이 됩니다.


##### 배열의 인덱스

```java
int[] s = new int[5];
```

##### 이름 공유
배열은 하나의 이름을 공유합니다.


##### 값의 핟당

```java
s[0] = 50;
```

예제코드) 배열을 이용하여 값 할당하기
```java
package ch03.study;

public class ArrayTest1 {

	public static void main(String[] args) {
		int[] s = new int[10]; // 변수선언
		
        // 반복문을 이용하여 값 할당.
		for (int i=0; i<s.length; i++) {
			s[i] = i;
		}
		
        // 반복문을 이용하여 값 읽기
		for (int i=0; i<s.length; i++) {
			System.out.print(s[i] + ",");
		}

	}

}
```

> 코드설명  
배열변수뒤에 `.length`를 붙이게 되면, 배열의 갯수를 출력합니다. 배열의 선언의 크기가 가변적일 수 있기 때문에 상수 보다 갯수를 파악하여 사용합니다.  
for문은 기능별로 구별하기 위해서 2번 반복하여 사용 합니다.  

> 출력결과
```
0,1,2,3,4,5,6,7,8,9,
```

예제코드) 성적 평균 구하기
```java
package ch03.study;

import java.util.Scanner;

public class ArrayTest2 {

	public static void main(String[] args) {
		final int STUDENTS = 5; // 상수 선언
		int total = 0;
		Scanner scan = new Scanner(System.in);
		
		// 배열 선언
		int[] score = new int[STUDENTS]; // 상수를 이용하여 크기 지정

		// 입력부 :
		for (int i=0; i<score.length; i++) {
			System.out.print("성적을 입력하시오: ");
			score[i] = scan.nextInt();
		}
		
		// 계산부: 합계
		for (int i=0; i<score.length; i++) {
			total += score[i];
		}
		
		System.out.println("평균 성적은 "+ total / STUDENTS + " 입니다.");
	}

}
```

출력결과
```
성적을 입력하시오: 10
성적을 입력하시오: 20
성적을 입력하시오: 30
성적을 입력하시오: 40
성적을 입력하시오: 50
평균 성적은 30 입니다.
```

##### 인덱스 오류

```java
int[] scores = new int[5]; // 5개의 배열 크기

scores[0] = 10; // 0부터 시작됨.
scores[1] = 10;
scores[2] = 10;
scores[3] = 10;
scores[4] = 10;
scores[5] = 10; // 오류 <== 선언된 배열의 크기를 넘어선 값지정
```

##### 다중 초기값 지정

```
int[] scores = {10, 20, 30, 40, 50};
```

중괄호를 이용하여 여러개의 값을 묽어서 할당할 수 있습니다.

배열을 선언할때 비어있는 `[]`를 사용하면, 크기가 고정되지 않는 배열을 선언할 수 있습니다.

예제코드)
```java
package ch03.study;

public class ArrayTest3 {

	public static void main(String[] args) {
		// 배열 초기화와 출력
		int[] scores = {10, 20,30, 40, 50};
		for (int i=0; i<scores.length; i++) {
			System.out.print(scores[i] + " ");
		}

	}

}
```

출력결과
```
10 20 30 40 50 
```

예제코드)
```java
package ch03.study;

public class GetMin {

	public static void main(String[] args) {
		// 최소값 찾기
		int s[]= {12, 3, 19, 6, 18, 8, 12, 4, 1, 19 };
		int min; // 최소값
		
		min = s[0]; // 최소값 초기화
		
		// 1부터 배열값을 비교함.
		// 0은 초기값으로 이미 사용되었음.
		for (int i=1; i<s.length; i++) {
			if (s[i] < min) min =s[i];
		}
		
		System.out.println("최소값은 = " + min);

	}

}
```

코드설명:
자료구조를 이용하여 2개의 값을 순차적으로 비교 합니다.

출력결과
```
최소값은 = 1
```

코드실습)
```java
package ch03.study;

public class RollDice {

	public static void main(String[] args) {
		// 주사위, 랜점값 출력하기
		final int SIZE = 6;
		int freq[] = new int[SIZE]; // 주사위 6면 지정
		
		for (int i=0; i<10000; i++) {
			// 각윤면에 대하여 처리
			++freq[(int)(Math.random() * SIZE)];
		}
		
		System.out.println("면빈도");
		for (int i=0; i<SIZE; i++) {
			System.out.println((i+1) + "=" + freq[i]);
		}
		
	}

}
```

출력결과
```
면빈도
1=1734
2=1645
3=1667
4=1658
5=1607
6=1689
```

예제코드)
```java
package ch03.study;

public class ArrayTest4 {

	public static void main(String[] args) {
		// 배열원소 출력
		int[] numbers = {10, 20, 30};

        // for..each문을 사용
		for (int value : numbers) {
            // 배열에서 하나의 요소를 가지고 옵니다.
			System.out.print(value + " ");
		}

	}

}
```

출력결과
```
10 20 30 
```

##### 배열복사
참조를 이용한 복사
```java
int[] a = {1, 2, 3, 4, 5};
int[] b = a;
```

클래스를 이용하여 복사

```java
int[] b = Arrays.copyOf(a, a.length);
```


예제코드)
```java
package ch03.study;

import java.util.Arrays;

public class SortTest {

	public static void main(String[] args) {
		// 숫자 정렬
		final int SIZE = 10;
		int[] numbers = new int[SIZE];
		
		// 램덤 데이터 저장
		for (int i=0; i<SIZE; i++) {
			int r = (int)(Math.random() * 100); // 0~99 중 하나
			numbers[i] = r;
		}
		
		System.out.print("리스트: ");
		for (int r:numbers) {
			System.out.print(r + " ");
		}
		Arrays.sort(numbers); // Arrays 클래스를 이용하여 정렬
		
		System.out.print("\n정렬값: ");
		for (int r: numbers) {
			System.out.print(r + " ");
		}		

	}

}
```

출력결과
```
리스트: 15 71 48 2 46 14 8 32 87 60 
정렬값: 2 8 14 15 32 46 48 60 71 87 
```


#### 2차원 배열
1개 이상의 복합구조를 가지는 배열을 다차원 배열이라 한다.

```java
int[][] s = new int[3][4];
```
2차원 배열은 `행`과 `열`을 가지고 있다.


3행 4열
```
int[][] arr = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};
```

예제코드)
```java
package ch03.study;

public class ArrayTest5 {

	public static void main(String[] args) {
		// 2차원 배열
		int[][] arr = {
			    {1, 2, 3, 4},
			    {5, 6, 7, 8},
			    {9, 10, 11, 12}
			};
		
		for (int i=0; i<arr.length; i++) {
			for ( int j=0; j<arr[i].length; j++) {
				System.out.println(i + "행" + j + "열" + arr[i][j]);
			}
		}

	}

}
```

출력내용
```
0행0열1
0행1열2
0행2열3
0행3열4
1행0열5
1행1열6
1행2열7
1행3열8
2행0열9
2행1열10
2행2열11
2행3열12
```


### 배열의 구조
1차원 배열


0부터 시작
배열은 0부터 시작합니다.

다차원 배열

Array 클래스

