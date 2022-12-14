## 03-1 기본 연산자
* 향과 연산자
	- 항(operand): 연산에 사용하는 값 / ex) 3, 4
	- 연산자(operator): 연산에 사용하는 기호 / ex) +
		+ 단항 연산자: 항이 한 개인 연산자 / ex) ++num
		+ 이항 연산자: 항이 두 개인 연산자 / ex) 사칙연산
		+ 삼항 연산자: 항이 세 개인 연산자 / ex) 조건 연산자
	- 연산자 우선순위  
		: 단항 연산자 > 이항 연산자 > 삼항 연산자

* 대입 연산자(assignment operator)  
	: 변수에 값을 대입하는 연산자
	- 이항 연산자 중 우선순위가 가장 낮은 연산자임 -> 모든 연산을 다 끝낸 후, 마지막에 연산 결과를 변수에 대입
	```
	totalScore = mathScore + engScore; // 1. mathScore과 engScore을 더함 2. totalScore 변수에 대입
	```
	- lValue  
		: 대입 연산자를 기준으로 왼쪽에 있는 변수 / 항상 변수 or 상수(10 등의 숫자는 올 수 없음)
	- rValue  
		: 대입 연산자를 기준으로 오른쪽에 있는 변수 / 변수 or 숫자(상수)가 올 수 있음
		+ 대입 연산자를 사용하면, rValue 값을 가져와서 lValue에 대입함

* 부호 연산자
	- ```+```  
		: 변수나 상수 값을 양수로 만듦
	- ```-```  
		: 변수나 상수 값을 음수로 만듦
	```
	public class Operator1 {
	    public static void main(String[] args){
	        int num = 10;
	
	        System.out.println(+num); // @@ 10
	        System.out.println(-num); // @@ -10 / num 값이 실제로 바뀌지는 않음
	        System.out.println(num); // @@ 10
	
	        num = -num; // num 값을 음수로 바꿔서 num에 저장
	        System.out.println(num); // @@ -10
	    }
	}
	```

* 산술연산자
	- ```+```  
		: 두 항을 더합니다
	- ```-```  
		: 앞에 있는 항에서 뒤에 있는 항을 뺍니다
	- ```*```  
		: 두 항을 곱합니다
	- ```/```  
		: 앞에 있는 항에서 뒤에 있는 항을 나누어 몫을 구합니다
	- ```%```  
		: 앞에 있는 항에서 뒤에 있는 항을 나누어 나머지를 구합니다

	- 산술 연산자 우선순위
		+ 일반 수학의 산술 연산과 같음
		+ ```%``` 연산자의 우선순위는 ```*```, ```/``` 연산자의 우선순위와 동일

* 증가/감소 연산자
	+ 단항 연산자
	+ 연산자의 앞/뒤에 사용
	+ 값을 1만큼 늘림/줄임
	+ ```++```  
		: 항의 값에 1을 더함
	```
	val = ++num; // num 값이 1 증가 -> 이후 val 변수에 대입
	val = num++; // val 변수에 대입 -> 이후 num 값이 1 증가
	```
	+ ```--```  
		: 항의 값에 1을 뺌
	```
	val = --num; // num 값이 1 감소 -> 이후 val 변수에 대입
	val = num--; // val 변수에 대입 -> 이후 num 값이 1 감소
	```

	+ 증가/감소 연산자의 위치
		+ ```;```: 문장 끝에 우이치
		+ 증가/감소 연산자가 피연자 앞에 있는 경우, 문장이 끝나기 전에 피연산자 값이 증가/감소

* 관계 연산자(= 비교 연산자)  
	: 두 개의 항 중 어느 것이 더 큰지, 작은지 등의 여부를 검사
	+ 이항 연산자
	+ 결과 값: true / false
	+```>```: 왼쪽 항이 크면 참, 아니면 거짓
	+```<```: 왼쪽 항이 작으면 참, 아니면 거짓
	+```>=```: 왼쪽 항이 크거나 같으면 참, 아니면 거짓
	+```<=```: 왼쪽 항이 작거나 같으면 참, 아니면 거짓
	+```==```: 두 개 항의 값이 같으면 참, 아니면 거짓
	+```!=```: 두 개 항의 값이 다르면 참, 아니면 거짓
	```
	boolean value = (my Age > 25); // 괄호로 가독성을 높임
	```

* 논리 연산자  
	- 우선순위: 관계 연산자 > 논리 연산자  
	- ```&&```: (and) 두 항이 모두 참인 경우에만 참, 그 외는 거짓  
	- ```||```: (or) 두 항 중 하나의 항만 참이면 참, 그 외는 거짓  
	- ```!```: 참인 경우는 거짓으로, 거짓인 경우는 참으로 바꿈(단항 연산자)  
	- 단락 회로 평가(SCE: Short Circuit Evaluation)  
		: 논리 곱, 논리 합 연산을 하는 경우, 두 항을 모두 실행하지 않아도 결과 값을 알 수 있으면 나머지 항은 실행되지 않는 것  
	```
	public class Operator3 {
	    public static void main(String[] args){
	        int num1 = 10;
	        int i = 2;

	        boolean value = ((num1 = num1 + 10) < 10) && ((i = i + 2) < 10); // (num1 = num1 + 10) < 10): 거짓 -> ((i = i + 2) < 10)가 실행되지 않음
	        System.out.println(value); // @@ false
	        System.out.println(num1); // 실행됨 @@ 20
	        System.out.println(i); // 실행되지 않음 @@ 2

	        value = ((num1 = num1 + 10) > 10) || ((i = i + 2) < 10); // (num1 = num1 + 10) > 10): 참 -> 논리합은 1개 항만 참이어도 참 -> 뒷 항은 의미 없음 -> ((i = i + 2) < 10)가 실행되지 않음
	        System.out.println(value); // @@ true
	        System.out.println(num1); // 실행됨 @@ 20
	        System.out.println(i); // 실행되지 않음 @@ 2


	    }
	}
	```
* 복합 대입 연산자  
	: 대입 연산자와 다른 연산자를 조합해 하나의 연산자처럼 사용하는 연산자
	+ 우선순위가 가장 낮음
	+ ```+=```  
		: 두 항의 값을 더해서 왼쪽 항에 대입
	+ ```-=```  
		: 왼쪽 항에서 오른쪽 항을 빼서 그 값을 왼쪽 항에 대입
	+ ```*=```  
		: 두 항의 값을 곱해서 왼쪽 항에 대입
	+ ```/=```  
		: 왼쪽 항에서 오른쪽 항을 나누어 그 몫을 왼쪽 항에 대입
	+ ```%=```  
		: 왼쪽 항에서 오른쪽 항을 나누어 그 나머지 값을 왼쪽 항에 대입
	+ ```<<=```  
		: 비트를 왼쪽으로 이동하고 그 값을 왼쪽 항에 대입
	+ ```>>=```  
		: 비트를 오른쪽으로 이동하고 그 값을 왼쪽 항에 대입(왼쪽에 채워지는 비트 값 = 부호 비트)
	+ ```>>>=```  
		: 비트를 왼쪽으로 이동하고 그 값을 왼쪽 항에 대입(왼쪽에 채워지는 비트 값 = 0)
	+ ```&=```  
		: 두 항의 & 연산 후 그 값을 왼쪽 항에 대입
	+ ```|=```  
		: 두 항의 | 연산 후 그 값을 왼쪽 항에 대입
	+ ```^=```  
		: 두 항의 ^ 연산 후 그 값을 왼쪽 항에 대입

* 조건 연산자
	+ 삼항 연산자
	```
	public class Operator4 {
	    public static void main(String[] args){
	        int fatherAge = 45;
	        int motherAge = 47;
	
	        char ch;
	        ch = (fatherAge > motherAge) ? 'T' : 'F'; // (fatherAge > motherAge)가 참이면 'T', 거짓이면 'F'를 ch에 대입
	        System.out.println(ch); // 실행되지 않음 @@ F
	    }
	}
	```


## 03-2 비트 연산자
* 비트 연산자  
	: 비트 단위로 연산이 이루어지는 연산자
	- (자바에서는) 프로그램에서 특정 값을 만들거나 연산할 때 사용
	- 그 외 사용
		+ 암호화 작업처럼 임의의 숫자를 만듦
		+ 마스킹(masking): 어떤 변수의 특정 비트를 꺼내봄
		+ 하드웨어에 내장되는 임베디드 시스템 프로그램에서 메모리 용량 부족/복잡한 계산으로 속도가 느려질 때, 2, 4배수를 만들어 속도 높임

* 비트 논리 연산자
	- ```&``` 연산자
		: 두 개의 비트 값이 모두 1인 경우에만 결과 값이 1이 됨
		```
		int num1 = 5;		       ->  num1: 00000101
		int num2 = 10;		         & num2: 00001010
		int ressult = num1 & num2;      result: 00000000
		```
	- ```|``` 연산자
		: 두 개의 비트 값이 한 개 이상 1인 경우에 결과 값이 1이 됨
		```
		int num1 = 5;		       ->  num1: 00000101
		int num2 = 10;		         | num2: 00001010
		int ressult = num1 | num2;      result: 00001111
		```
	- ```^``` 연산자
		: 같은 값이면 0, 다른 값이면 1의 결과 값을 가짐
		```
		int num1 = 5;		       ->  num1: 00000101
		int num2 = 10;		         ^ num2: 00001010
		int ressult = num1 ^ num2;      result: 00001111
		```
	- ```~``` 연산자(= 반전 연산자)
		: 0을 1로, 1은 0으로 바꿈
		```
		int num = 10;		       ->  num: 00001010
		int ressult = ~num;		          ~num: 00001010
		```

* 비트 이동 연산자(= 시프트 연산자)
	- ```<<``` 연산자  
		: 왼쪽으로 비트를 이동
		```
		int num = 5;		       ->  num1: 00000101
		num << 2;		           num << 2: 00010100 // 앞의 두자리 비트 00은 삭제 + 뒷부분은 0으로 채움
		```
	- ```>>``` 연산자  
		: 오른쪽으로 비트를 이동
		```
		int num = 5;		       ->  num1: 00000101
		num >> 2;		           num << 2: 00000001 // 뒤의 두자리 비트 01은 삭제 + 앞부분은 부호비트와 동일하게(0) 채움
		```
	- ```>>>``` 연산자  
		: 오른쪽으로 비트를 이동 + 왼쪽에 채워지는 비트 값이 무조건 0
		```
		int num = 5;		       ->  num1: 00000101
		num >> 2;		           num << 2: 00000001 // 뒤의 두자리 비트 01은 삭제 + 앞부분은 0으로 채움
		```
	- num 자체 값은 변화 없음 -> 대입 필요

* 연산자 우선순위
	- 단항 연산자 > 이항 연산자 > 삼항 연산자
	- 대입 연산자의 우선순위가 가장 낮음
	- 산술 > 관계 > 논리> 대입
	- ()의 우선순위가 가장 높음  
  ![image](https://user-images.githubusercontent.com/104348646/193457716-ebfd9999-236f-4612-8675-02b7da62a4d5.png)  
