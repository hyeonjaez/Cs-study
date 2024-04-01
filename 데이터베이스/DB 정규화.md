# DB 정규화

- 데이터의 중복을 최소화하게 데이터를 구조화 하는 프로세스를 정규화 라고 하는데 정규화의 목표는 이상이 있는 관계를 재구성해서 작고 잘 조직된 관계를 생성하는 것 이다.


### 목적
---

- 불필요한 데이터를 제거 하고 데이터의 중복을 최소화 하는 것
- 삽입/갱신/삭제 시 발생할 수 있는 이상 현상을 방지하기 위해
	- 삽입 이상 : 데이터를 저장  때 원하지 않는 정보가 함께 사입되는 것
	- 삭제 이상 : 특정 값을 삭제 할때 유지되어야 하는 정보까지 삭제 되는 경우
	- 갱신 이상 : 특정값을 갱신 시킴으로써 정보의 모순성이 발생


![Pasted image 20231101161551](https://github.com/hyeonjaez/Cs-study/assets/50399586/eb428bfc-83d4-4a71-a725-d8e155b8aaf9)



### 1. 정규화
---

- 같은 성격과 내용의 컬럼이 연속적으로 나타나는 컬럼이 존재할 때 해야함
- 테이블의 컬럼이 원자값을 갖도록 테이블을 분해하는 것
- 기본의 테이블과 1:N 관계를 형성 하는 것

![Pasted image 20231101162758](https://github.com/hyeonjaez/Cs-study/assets/50399586/9616b241-2531-4ab0-ae3f-d863e3761660)


![Pasted image 20231101162827](https://github.com/hyeonjaez/Cs-study/assets/50399586/9ac3310b-c923-440e-85f6-7686a09bd853)


### 2. 정규화
---

- PK가 여러 키로 구성된 복합키로 구성된 경우일때 해야한다.
- 1 정규화를 진행한 테이블에 대해 완전 함수 종속을 만족하도록 테이블을 분해하는 것
- 기본키의 부분집합이 결정자가 되어선 안된다

![Pasted image 20231101162827](https://github.com/hyeonjaez/Cs-study/assets/50399586/68ac248d-ebd5-4ddb-84f4-8851a56654b3)


![Pasted image 20231101163154](https://github.com/hyeonjaez/Cs-study/assets/50399586/5de16f8f-60ba-4786-8203-f2e88e9c6657)




### 3. 정규화
---

- 테이블의 컬럼들이 기본키가 아닌 다른 일반 컬럼에 의존하는 컬럼들이 있을 때 해야함
- 2 정규화를 진행한 테이블에 대해 이행적 종속을 없애도록 테이블을 분해하는 것
- A -> B, B -> C 일때 A -> C가 성립되는 것

![Pasted image 20231101165957](https://github.com/hyeonjaez/Cs-study/assets/50399586/f2d70793-84b7-4a75-a636-a8e3304aceaa)


![Pasted image 20231101163154](https://github.com/hyeonjaez/Cs-study/assets/50399586/78edf72a-1ad9-40e7-85cd-3d2d39ca9a6b)



