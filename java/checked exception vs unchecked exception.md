# checked exception vs unchecked exception

우선, Exception과 Error의 상속 관계이다.

![Pasted image 20231025232848](https://github.com/hyeonjaez/Cs-study/assets/50399586/c26323a7-625f-468c-804b-a8a808ee527d)

Exception 과 Error는 최상위 Object를 상속받는 Throwable Class를 상속받는 Class 이다.

결론적으로 말하면 
- Checked Exception은 error와 RuntimeException을 상속하지 않은 Exception Class를 의미하고
- Unchecked Exception은 RuntimeException을 상속받는 Exception Class를 의미한다.

- 다시 말해 꼭 처리해야 하는 Exception은 Checked Exception이고,
명시적으로 처리하지 않아도 되는 Exception은 Unchecked Exception이다.




## Error
---

- 에러는 시스템에 비정상적인 상황이 발생했을 경우에 발생한다.
- 메모리 부족(OutofMemoryError)이나 스택오버플로우(StackOverflowError)와 같이 복구할 수 없는 것을 말한다.
- 에러는 개발자가 예측하기도 쉽지 않고 처리할 수 있는 방법도 없다.



## Exception
---

- 예외는 프로그램 실행 중에 개발자의 실수로 예기치 않은 상황이 발생했을 때를 말한다.
- 예를 들면 범위를 벗어난 ArrayIndexOutOfBoundsException이나 NullPointerException 등과 같이 심각한 오류가 아닌 개발자의 실수로 발생한 것들을 말한다.

- 예외에는 Cheked Exception 과 Unchecked Exception으로 나뉜다.
- 계층 구조로 보면 RuntimeException의 하위 클래스들이 Uncheck Exception 이라 한다.


### Checked Exception
---

- 반드시 에러 처리를 해야하는 특징을 가지고 있다.
- 계층 구조로 보면 RuntimeException의 하위 클래스가 아니면서 Exception 클래스의 하위 클래스들이다.



### Unchecked Exception
---
- 체크 예외와는 달리 에러 처리를 강제하지 않는다.
- 실행 중에 발생할 수 있는 예외를 의미한다.
- 계층 구조로 보면 RuntimeException의 하위 클래스들을 의미한다.



[**언체크 예외는 예외처리를 강제하지 않는 이유**]

만약 Unchecked Exception을 강제해야 했다면 어땠을까?

```java
public class ArrayTest { 
	public static void main(String[] args) { 
		try { 
			int[] list = {1, 2, 3, 4, 5};
			System.out.println(list[0]); 
			} catch (ArrayIndexOutOfBoundsException e) { 
				e.printStackTrace(); 
			} 
	} 
}
```

단순하게 이런식으로 해도 try/catch문을 써야한다. 
이러한 RuntimeExceptiond은 개발자들에 의해 실수로 발생하는 것들이기 때문에 에러를 강제하지 않는다.




![Pasted image 20231025235431](https://github.com/hyeonjaez/Cs-study/assets/50399586/08149bfd-65f9-4c8f-94f7-028dbfd8af67)



- Checked Exception이 Rollback되지 않는 이유

기본적으로 Checked Exception은 복구가 가능하다는 메커니즘을 가지고 있다.  
예를 들어, 특정 이미지 파일을 찾아서 전송해 주는 함수에서 이미지를 찾지 못 했을 경우 기본 이미지를 전송한다는 복구 전략을 가질 수 있다. 정리하자면, 복구가 가능하니 Rollback은 진행하지 않는다는 의미이다.




### Checked Exception vs UnChecked Exception 선택하기
---

- 임의의 예외 클래스를 만들어 예외 처리를 하는 경우가 많을 것인데요. 이 때 try-catch로 묶어줄 필요가 있을 경우에만 Exception 클래스를 확장합니다.
-  일반적으로 실행시 예외를 처리할 수 있는 경우에는 RuntimeException 클래스를 확장해 Unchecked Exception 을 사용하는 것이 좋습니다.
