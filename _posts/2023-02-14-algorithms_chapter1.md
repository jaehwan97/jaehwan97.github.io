---
layout: post
title:  "기본 알고리즘 "
---

# 기본 알고리즘 

> 1-1 알고리즘이란?

<h4>정의: 어떤 문제를 해결하기 위한 절차로, 명확하게 정의되고 순서가 있는 유한 개의 규칙으로 이루어진 집합</h4>

즉 어떠한 문제 해결을 위한 방법과 절차를 알고리즘이라고 부른다. 

<h4>속성: 알고리즘은 유한성을 가지며 언젠가는 끝나야하는 속성을 가지고 있다.</h4>

<h4>알고리즘의 5가지 조건</h4>

입력:외부에서 제공되는 자료가 0개이상 존재해야 합니다.

출력:적어도 2개이상의 서로 다른 결과를 내어야합니다.

명확성:수행과정은 무엇을 하기위한 것인지 명확하게 정의해야 합니다.

유한성:알고리즘의 명령어대로 수행했을 때 처리된 후 종료되어야합니다.

효율성:모든 과정은 명백하게 실행가능한 것이어야 하며,시간적 공간적 효율성을 가져야합니다.

<h2> 알고리즘의 표현</h2>

1.자연어 

2.순서도

3.프로그래밍언어

#### 좋은 알고리즘이란 

효율성을 고려하여 작성한 알고리즘이 좋다고 평가 받으며 알고리즘의 성능을 분석할때는 공간복잡도와 시간복잡도를

계산합니다.

공간복잡도: 총 저장공간의 양

시간 복잡도: 총 소요시간

시간복잡도 3가지 유형

빅-오메가:최선일때의 연산 횟수

빅-세타:보통일때의 연산 횟수

★빅-오:최악일떄의 연산 횟수 (대부분의 코딩테스트는 빅-오를 기준으로 합니다.)

<h3> 3개의 정숫값을 입력하고 최댓값을 구하여 출력하는 알고리즘</h3>

```java
int max=a;
if(b>max)max=b;
if(c>max)max=c;
```

절차를 보면 

1.max에 a값을 넣습니다. 

2.b값이 max보다 크면 max에 b값을 넣습니다.

3.c값이 max보다 크면 max에 c값을 넣습니다.

이런식으로 구성되어 있는데 이렇게 여러 문장이 순차적으로 실행되는 구조를 순차(sequential)구조라고 합니다.

또한 if문을 따라 실행 흐름을 변경하는 if문을 선택(selection) 구조라고 합니다.

<h2> Q1 네 값의 최댓값을 구하는 max4 메서드를 작성하세요. 작성한 메서드를 테스트하기 위해 main 메서드를 포함한 프로그램을 작성해야합니다.</h2>

```java
static int max4(int a,int b,int c,int d)
```

정답

```java
class Max4 {
	static int max4(int a, int b, int c, int d) {
		int max = a;					
		if (b > max) max = b;
		if (c > max) max = c;
		if (d > max) max = d;
		return max;
	}
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int a, b, c, d;

		System.out.println("네 정수의 최댓값을 구합니다.");
		System.out.print("a의 값 : ");  a = sc.nextInt();
		System.out.print("b의 값 : ");  b = sc.nextInt();
		System.out.print("c의 값 : ");  c = sc.nextInt();
		System.out.print("d의 값 : ");  d = sc.nextInt();

		int max = max4(a, b, c, d);	//메서드 사용

		System.out.println("최댓값은 " + max + "입니다.");
	}
}
```

## Q2 세 값의 최솟값을 구하는 min3 메서드를 작성하세요.

```java
		int min = a;			
		if (b < min) min = b;
		if (c < min) min = c; 
		//(중요 부분만 기술)
```

## Q3 네 값의 최솟값을 구하는 min4 메서드를 작성하세요.

```java
int min = a;			
		if (b < min) min = b;
		if (c < min) min = c; 
		if (d < min) min = d; 
```



<img src="https://media.licdn.com/dms/image/C4E12AQG19i3vFGtvtw/article-cover_image-shrink_600_2000/0/1632989308365?e=2147483647&v=beta&t=mSbfIORcvABLFlOihK1zruT8Hyabj2RlHTCNDU2qr6w" style="width:1000px;height:500px" />

##결정트리

<img src="https://i.ytimg.com/vi/vQVZVVkOQU4/maxresdefault.jpg" style="width:1000px;height:500px" />

## 순서도





## Q4 세 값의 대소 관계인 13가지 조합의 중앙값을 구하여 출력하는 프로그램을 작성하세요.

```JAVA
		if (a >= b) //1C-1 그대로
			if (b >= c)
				return b;
			else if (a <= c)
				return a;
		else
			return c;
		else if (a > c)
			return a;
		else if (b > c)
			return c;
		else
			return b;
```

##Q5 중앙값을 구하는 메서드는 다음과 같이 작성할 수도 있습니다. 그러나 실습 1C-1의 med3메서드에 비해 효율이 떨어지는데 그 이유를 설명하세요.

```java
		if ((b >= a && c <= a) || (b <= a && c >= a)) //a
			return a;
		else if ((a > b && c < b) || (a < b && c > b))//b
			return b;
		return c;//c
해설참고:처음 if 문의 판단
　　  if ((b >= a && c<= a) || (b <= a && c >= a)
 에 주목합니다. 
  여기서 b >= a 및 b <= a의 판단을 뒤집은 판단
  (실질적으로 동일한 판단)이, 계속하여  else 이후에서
　　 else if ((a > b && c < b) || (b <= a && c > b)
  로 수행됩니다. 즉, 처음 if가 성립하지 않는 경우,
  2번째 if에서도 (실질적으로 ) 같은 판단을 수행하므로,
  효율이 나빠집니다.

```



# 순서도

문제의 정의, 분석, 해법을 그림으로 표현하는 순서도의 대표 용어와 기호

프로그램 순서도에서 사용하는 기호

1. 실제로 실행할 연산을 나타내는 기호
2. 제어 흐름을 나타내는 선 기호
3. 프로그램 순서도를 이해하거나 작성하는데 편리한 특수 기호 

####데이터

데이터의 입력과 출력을 나타냅니다.    

####처리

처리는 여러 종류의 처리 기능을 나타냅니다. 예를 들어 정봇값,자료형,위치를 바꾸도록 정의한 연산의 실행 또는 연속하는 몇 가지 흐름 가운데 하나의 방향을 결정하는 연산의 실행을 나타냅니다.

#### 미리 정의된 처리

미리 정의된 처리는 서브루틴 및 모듈등 다른곳에서 이미 정의된 하나 이상의 연산 또는 여러개의 명령어로 이루어진 처리를 나타냅니다.

#### 판단

하나의 입구와 하나의 선택하는 몇개의 출구가 있고, 기호에서 정의한 조건을 평가하여 하나의 출구를 선택하는 판단기능을 나타냅니다.

####루프범위

두 부분으로 구성되어 루프의 시작과 종료를 나타냅니다. 루프의 시작 기호 또는 종료 기호안에 초깃값,증갓값,종룟값을 표기합니다.

#### 선

제어의 흐름을 나타냅니다. 순서도에서 흐름의 방향을 분명히 나타내고자 할때, 또는 보기 쉽게 하기 위해 화살표를 붙이기도 합니다.

#### 단말

외부 환경으로 나가거나 외부 환경에서 들어오는 것을 나타냅니다. 예를 들어 프로그램 흐름의 시작과 종료를 나타냅니다.



> ###1-2 반복

반복문을 사용한 간단한 알고리즘들

1부터 N까지의 정수의 합구하기 

```JAVA
//while문
while( i<=n ){
  sum+=i;
  i++;
}
//for문
for(int i=1;i<=n;i++)
  sum+=i;
```

while(루프)문은 사전판단반복으로 실행전에 계속할지를 판단 즉 조건이 참이어야 실행

for문은 하나의 변수를 사용하는 반복문에 적합하다.  저어식을 평가한 값이 true이면 반복문을 실행한다. (순서도에서 루프문으로 둘러싸인 부분)



## Q7 가우스의 덧셈법 사용해서 1부터 N까지의 정수합을 구하는 프로그램을 작성하세요.

```JAVA
int n=10;
int result;

result=(1+n)*(n/2);
if(n%2!=0){
	result+=(n+1)/2; //가운데 남은 홀수 더해줌
}
```



##Q8 정수 A,B를 포함하여 그 사이의 모든 정수의 합을 구하여 반환하는 메서드를 작성하세요.

```JAVA
int sum=0;
for(int i= min; min <= max;i++){
  sum+=i;
}
```



###사용자에게 양수만 입력하게 하기

```java
do{
  System.out.print("값:");
  n=sc.nextInt();
}while(n<=0); //do while문은 일단 한번 실행되고 조건식 검사를 한다. (사후판단반복)
```



## Q9 오른쪽 결과와 같이 두 변수 A,B에 정수를 입력하고 B-A를 출력하는 프로그램을 작성하세요.

```java
		Scanner sc = new Scanner(System.in);

		System.out.print("a의 값 : ");
		int a = sc.nextInt();

		int b; 
		while (true) {
			System.out.print("b의 값 : "); 
			b = sc.nextInt(); 
			if (b > a) break; //b값이 더 큰 경우에만 넘어갈 수 있음
			System.out.println("a보다 큰 값을 입력하세요!");
		}

		System.out.println("b - a는 " + (b - a) + "입니다.");
```



## Q10 양의 정수를 입력하고 자릿수를 출력하는 프로그램을 작성하세요. 예를 들어 135를 입력하면 '그 수는 3자리입니다.'라고 출력하고, 131를 입력하면 '그 수는 4자리 입니다.'라고 출력합니다.

```java
int n;
do {
	System.out.print("정숫값 : ");
	n = stdIn.nextInt();
} while (n <= 0);

int number=0;
while(n>0){
	n/=10;
  number++;
}
System.out.println(n+"은 " + number + "자리입니다.");
```



###┌ 반복 과정에서 조건 판단하기  

반복횟수를 줄이는 방향으로 판단하자 (제일)많이 반복되는 과정에서 불필요한 연산이 껴있다면 반복 밖으로 따로 빼주자.

@ += , /= 등 대입연산자



### +-번갈아서 출력하기

```java
for(int i =0; i<n; i++){
  if(i%2==0)
    System.out.print("+");
  else()
    System.out.print("-");
}

// i가 짝수이면 + 홀수이면 -를 출력한다.
```

위 코드의 문제점 2가지 

1.반복할 때마다 if문이 실행됩니다. for문을 실행할 때마다 if문을 실행하므로 i값이 홀수인지 알아내기 위해 if문을 모두 n번 실행해야합니다. 

2.유연한 대처가 어렵습니다. i를 0이아닌 다른 수부터 시작하려면 코드 전체를 손봐야 합니다.

### 수정안

```java
for(int i=0; i<n/2;i++){System.out.print("+-");}
if(n%2 !=0 ){System.out.print("+");}
```

1.for문은 +-를 n/2 회 출력합니다. 예를 들어 n 값이 12이면 6번 , 15번이면 7번출력합니다. 그러므로 짝수이면 for문만 출력합니다.

2.n이 홀수일 때에만 +를 출력합니다.

*를 n개 출력하되 w개마다 줄 바꿈 프로그램

```java
for(int i=0;i<n/w;i++){ //1
  System.out.println("*".repeat(w));
}
int rest = n%w; //2
if(rest !=0){
  System.out.println("*".repeat(rest));
}			
```

1.*를 w개 출력하면서 n/w번 실행합니다. 즉 ,for문에서 *를 w개 출력하는 것을 n/w번 실행합니다.

2.*를 n%w번 출력하고 줄바꿈을 합니다. 															    

​																							┘

###논리연산과 드모르간 법칙

|| 하나라도 참이면 (논리합)

&& 둘다 참이어야함 (논리곱)

단축평가: 한쪽을 평가하면 반대쪽을 평가하지 않아도 되는 경우가 많아 시간을 아낄 수 있다.

####드모르간 법칙: 각 조건을 부정하고 논리곱을 논리합으로, 논리합을 논리곱으로 바꾸고 다시 전체를 부정하면, 원래의 조건과 같다.

ex) 

x&&y 와 !(!x || !y)는 같다.

x || y와 !(!x && !y)는 같다.

#### 구조적 프로그래밍이란?

입력하는 곳 하나와 출력하는 곳 하나를 갖는 구성 요소만을 사용하여, 이들을 계층적으로 배치하여 프로그램을 구성하는 방식을 구조적 프로그래밍이라고 합니다.구조적 프로그래밍은 순차,선택,반복이라는 세 종류의 제어 흐름을 사용합니다.



## 다중 루프 다루기

반복안에서 다시 반복

```java
//대표적인 다중 루프인 구구단 예시
for(int i=1;i <= 9; i++){ //행
  for(int j=1; j <= 9; j++) //열
    System.out.printf("%3d",i*j);
  System.out.println();
}
```



##Q11 오른쪽 결과와 같이 위쪽과 왼쪽에 곱하는 수가 있는 구구단 곱셈표를 출력하는 프로그램을 작성하세요.

```JAVA
		System.out.print("   |");
		for (int i = 1;i <= 9; i++) //위에는 따로 만들어줌
			System.out.printf("%3d", i);
		System.out.println("\n---+---------------------------"); //제일 처음만

		for (int i = 1; i <= 9; i++) { //구구단
			System.out.printf("%2d |", i); // 각 제일 처음에만
			for (int j = 1; j <= 9; j++)
				System.out.printf("%3d", i * j);
			System.out.println();
		}
```



## Q12 구구단 곱셈표를 변형하여 곱셈이 아니라 덧셈을 출력하는 프로그램을 작성하세요.

```java
		System.out.print("   |");
		for (int i = 1;i <= 9; i++) //위에는 따로 만들어줌
			System.out.printf("%3d", i);
		System.out.println("\n---+---------------------------"); //제일 처음만

		for (int i = 1; i <= 9; i++) { //구구단
			System.out.printf("%2d |", i); // 각 제일 처음에만
			for (int j = 1; j <= 9; j++)
				System.out.printf("%3d", i + j); //*만 +로 변경
			System.out.println();
		}
```



##Q13오른쪽 결과와 같이 입력한 수를 한 변으로 하는 정사각형을 *로 출력하는 프로그램을 작성하세요.

```JAVA
		for (int i = 1; i <= n; i++) { //N값은 따로 입력 받음
			for (int j = 1; j <= n; j++)
				System.out.print('*');
			System.out.println();
		}
```



## Q14 직각이등변삼각형을 출력하는 부분을 아래와 같은 형식의 메서드로 작성하세요.

static void triangleLB(int n) //왼쪽아래가 직각인 이등변삼각형을 출력

```java
	static void triangleLB(int n) { //왼쪽아래가 직각인 이등변삼각형을 출력
		for (int i = 1; i <= n; i++) {            
			for (int j = 1; j <= i; j++)           
				System.out.print('*');
			System.out.println();                  
		}
	}
```



## Q15 n단의 피라미드를 출력하는 메서드를 작성하세요.

``` java
		for (int i = 1; i <= n; i++) {				//몇 행까지
			for (int j = 1; j <= n - i; j++)		//띄어쓰기
				System.out.print(" ");				
			for (int j = 1; j <= (i-1)*2+1; j++)	//문제 제시 조건
				System.out.print("*");
			System.out.println();								
```



## Q16 오른쪽과 같이 아래를 향항 n단의 숫자 피라미드를 출력하는 메서드를 작성하세요.

```java
		for (int i = 1; i <= n; i++) {				
			for (int j = 1; j <= n - i; j++)		
				System.out.print(' ');
			for (int j = 1; j <= (i-1)*2+1; j++)	
				System.out.print(i % 10); 			//숫자로 출력
			System.out.println();						
		}
```

















