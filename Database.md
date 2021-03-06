# Database

## Contents  
[**1. 논리 데이터베이스 설계**](#1-논리-데이터베이스-설계)  
[**2. 물리 데이터베이스 설계**](#2-물리-데이터베이스-설계)  
[**3. SQL 응용**](#3-SQL-응용)  
[**4. SQL 활용**](#4-SQL-활용)  
[**5. 데이터 전환**](#5-데이터-전환)  

----

## 1. 논리 데이터베이스 설계
1. 데이터베이스 설계
	- 사용자 요구 분석해 DBMS로 데이터베이스를 구현해 사용하게 하는 것
	- 고려사항
		- 무결성
			- 삽입, 삭제, 갱신 후에도 저장된 데이터가 제약 조건 항상 만족해야 함
		- 일관성
			- 응답이 처음부터 끝까지 변함없이 일정해야 함
		- 회복
			- 시스템 장애 발생했을 때 장애 발생 직전의 상태로 복구할 수 있어야 함
		- 보안
			- 불법적인 데이터의 손실로부터 보호할 수 있어야 함
		- 효율성
			- 응답 시간 단축, 저장공간 최적화 등 가능해야 함
		- 데이터베이스 확장
			- 데이터베이스 운영 영향 주지 않고 지속적으로 데이터 추가할 수 있어야 함
	- 설계 순서
		1. 요구 조건 분석
			- 데이터베이스 사용할 사람들로부터 필요한 용도 확인
			- 수집 정보 바탕으로 요구 조건 명세 작성
		2. 개념적 설계
			- 현실 세계 인식을 추상적 개념으로 표현
			- 개념 스키마 모델링, 트랜잭션 모델링, ERD 작성
		3. 논리적 설계
			- DBMS가 지원하는 논리적 자료 구조로 변환(Mapping)시키는 과정
			- 논리 스키마 설계, 트랜잭션 인터페이스 설계
		4. 물리적 설계
			- 물리적 저장장치에 저장할 수 있는 물리적 구조 데이터로 변환
			- 고려사항: 트랜잭션 처리량, 응답 시간, 디스크 용량
		5. 데이터베이스 구현
			- 데이터베이스 스키마를 파일로 생성
			- DDL 이용해 스키마 기술, 데이터베이스 파일 생성

2. 데이터 모델의 개념
	- 현실 세계의 정보들을 단순화, 추상화해서 체계적으로 표현한 개념적 모형
	- 데이터베이스 설계 과정에서 데이터 구조(스키마)를 논리적으로 표현하기 위한 지능적 도구
	- 구성 요소
		- 개체 (Entity)
			- 데이터베이스에서 표현하려는 것, 현실 세계의 대상체
			- 유일한 식별자에 의해 식별 가능
		- 속성 (Attribute)
			- 데이터의 가장 작은 논리적 단위, 데이터 항목
			- 특징에 따른 분류
				- 기본 속성
					- 업무 분석을 통해 정의한 속성
				- 설계 속성
					- 설계 과정에서 도출해내는 속성
				- 파생 속성
					- 다른 속성으로부터 영향 받아 발생하는 속성
			- 개체 구성 방식에 따른 분류
				- 기본키 속성
					- 개체를 식별할 수 있는 속성
				- 외래키 속성
					- 다른 개체와의 관계에서 포함된 속성
				- 일반 속성
					- 개체에 포함되어있고 기본키, 외래키가 아닌 속성
		- 관계 (Relationship)
			- 개체간의 관계, 속성간의 논리적 연결
			- 형태
				- 1:1, 1:N, N:M
			- 종류
				- 종속 관계
					- 두 개체 사이 주-종관계 표현
					- 식별 관계
						- 한 개체의 존재 여부가 다른 개체의 존재 여부에 의존적인 경우
						- ERD에서 실선으로 표시
					- 비식별 관계
						- 한 개체의 존재 여부가 다른 개체의 존재 여부에 관계 없는 경우
						- ERD에서 점선으로 표시
				- 중복 관계
					- 두 개체 사이 2번 이상의 종속 관계가 발생하는 관계
				- 재귀 관계
					- 개체가 자기 자신과 관계를 갖는 것
				- 배타 관계
					- 개체의 속성이나 구분자 기준으로 개체 특성 분할하는 관계
					- 배타 AND 관계
						- 하나의 개체만 선택 가능
					- 배타 OR 관계로 구분
						- 하나 이상의 개체 선택 가능
	- 종류
		- 개념적 데이터 모델
			- 현실 세계에 대한 인식을 추상적 개념으로 표현하는 과정, 정보 모델
			- ex) E-R 모델
		- 논리적 데이터 모델
			- 개념적 구조를 컴퓨터에 맞도록 변환하는 과정, 데이터 모델
			- 품질 검증 : 개체, 속성, 관계, 식별자, 전반적인 품질 검증 항목
			- ex) 관계 모델, 계층 모델, 네트워크 모델
	- 표시 요소
		- 구조
			- 논리적으로 표현된 개체 타입들간의 관계
		- 연산
			- 실제 데이터를 처리하는 작업에 대한 명세
		- 제약 조건
			- 실제 데이터의 논리적인 제약 조건

3. 식별자 (Identifier)
	- 하나의 개체 내에서 각 인스턴스를 유일하게 구분할 수 있는 구분자
	- 분류
		- 대표성 여부
			- 주 식별자 (Primary Identifier)
				- 개체 대표하는 유일한 식별자
				- 한 개만 존재
				- 물리적 테이블에서 기본키(Primary Key)로 사용
				- 특징
					- 유일성
						- 주 식별자에 의해 개체 내 모든 인스턴스들 유일하게 구분되어야 함
					- 최소성
						- 주 식별자를 구성하는 속성의 수는 유일성을 만족하는 최소 수가 되어야 함
					- 불변성
						- 한 번 특정 개체에 지정되면 변하지 않아야 함
					- 존재성
						- 반드시 데이터 값이 존재해야 함
			- 보조 식별자 (Alternate Identifier)
				- 주 식별자 대신해 개체를 식별할 수 있는 속성
				- 한 개 이상 존재
				- 물리적 테이블에서 유니크 인덱스로 사용
			- 주 식별자, 보조 식별자 모두 개체를 유일하게 식별할 수 있어야 함
		- 스스로 생성 여부
			- 내부 식별자
				- 개체 내에서 스스로 만들어지는 식별자
			- 외부 식별자
				- 다른 개체와의 관계에 의해 외부 개체 식별자 사용하는 식별자
		- 단일 속성 여부
			- 단일 식별자
				- 한 가지 속성으로만 구성된 식별자
			- 복합 식별자
				- 두 개 이상의 속성으로 구성된 식별자
		- 대체 여부
			- 원조 식별자
				- 가공되지 않은 원래의 식별자
			- 대리 식별자
				- 두 개 이상의 속성들을 하나의 속성으로 묶어 사용하는 식별자

3. E-R 모델 (Entity-Relationship Model)
	- 개체간 관계를 기본 요소로 이용해 현실 데이터를 개념적인 논리 데이터로 표현  
	- 데이터를 개체, 관계, 속성으로 묘사  
	![image](https://user-images.githubusercontent.com/53277342/155987827-2b33cee7-d3bf-4717-87b5-3a0144767082.png)
	
3. 관계형 데이터 모델
	- 2차원적인 테이블을 이용해 데이터 상호 관계를 정의하는 DB 구조
	- 기본키와 외래키로 데이터 간의 관계 표현
	- 용어
		- 릴레이션
			- 데이터를 표의 형태로 표현한 것
			- 릴레이션 스키마: 구조
			- 릴레이션 인스턴스: 실제 값들
		- 튜플
			- 릴레이션 구성하는 각각의 행, 속성의 모임으로 구성
			- 레코드와 같은 의미
			- Cardinality: 튜플의 수
		- 속성
			- 데이터베이스 구성하는 가장 작은 논리적 단위
			- 데이터 항목, 데이터 필드에 해당, 객체의 특성 기술
			- Degree: 속성의 수
		- 도메인
			- 하나의 속성이 취할 수 있는 범위

5. 관계형 데이터베이스의 제약조건 (키)
	- 제약조건
		- 데이터 정확성 보장하기 위해 키를 이용해 입력 데이터에 제한 줌
	- 키
		- 튜플을 서로 구분할 수 있는 기준이 되는 속성
		- 종류
			- 후보키 (Candidate Key)
				- 튜플을 유일하게 식별 가능한 속성들의 부분집합
				- 기본키로 사용할 수 있는 속성
				- 특징
					- 유일성 (Unique)
						- 하나의 키 값으로 하나의 튜플만을 유일하게 식별 가능
					- 최소성 (Minimality)
						- 모든 레코드들을 유일하게 식별하는데 꼭 필요한 속성
			- 기본키 (Primary Key)
				- 후보키 중 특별히 선정된 주키 (Main Key)
				- 특징: 유일성, 최소성
				- NULL값 가질 수 없음
			- 대체키 (Alternate Key)
				- 후보키가 둘 이상일 때 기본키가 아닌 나머지 후보키
			- 슈퍼키 (Super Key)
				- 한 릴레이션 내 속성들의 집합으로 구성된 키
				- 특징: 유일성 O, 최소성 X
			- 외래키 (Foreign Key)
				- 다른 릴레이션의 기본키를 참조하는 속성																															

6. 관계형 데이터베이스의 제약조건 (무결성)
	- 무결성
		- 데이터베이스에 저장된 값과 현실 세계의 실제 값이 일치하는 정확성
		- 종류
			- 개체 무결성 (Entity Integrity)
				- 기본키를 구성하는 어떤 속성도 NULL값이나 중복값 가질 수 없음
			- 도메인 무결성 (Domain Integrity)
				- 주어진 값이 정의된 도메인에 속한 값이어야만 함
			- 참조 무결성 (Referential Integrity)
				- 외래키 값은 NULL이거나 참조 릴레이션의 기본키 값과 동일해야 함
			- 사용자 정의 무결성 (User-Defined Integrity)
				- 속성 값들이 사용자가 정의한 제약 조건에 만족해야 함
			- 데이터 무결성
				- 데이터 특성에 맞는 적절한 무결성 정의, 강화해야 함
				- 강화 방법
					- 어플리케이션
						- 무결성 조건 검증하는 코드를 프로그램 내 추가
						- 복잡한 규칙을 검토하는 무결성 검사는 어플리케이션 내에서 처리
					- 데이터베이스 트리거
						- 트리거
							- 이벤트가 발생할 때마다 자동으로 수행되는 절차형 SQL
						- 절차형 SQL 추가
						- 통합 관리 가능
					- 제약조건
						- 통합 관리 가능

7. 관계대수 및 관계해석
	- 관계대수
		- 데이터베이스에서 원하는 정보를 검색하기 위해 어떻게 유도하는지 기술하는 절차적 언어
		- 종류
			- 순수 관계 연산자
				- Select
					- 선택 조건을 만족하는 튜플의 부분집합 구함
				- Project
					- 속성 리스트에 제시된 속성 값만 추출
				- Join
					- 공통 속성 중심으로 두개의 릴레이션 하나로 합침
					- 릴레이션의 차수는 조인된 두 릴레이션의 차수 합
					- 자연 조인 (Natural Join)
						- 중복된 속성을 제거해 같은 속성을 한 번만 표기하는 방법
				- Division
					- 속성 모두 가진 튜플에서 한 집합이 가진 속성을 제외한 속성
			- 일반 집합 연산자
				- 합집합 (Union)
				- 교집합 (Intersection)
				- 차집합 (Difference)
				- 교차곱 (Cartesian Product)
	- 관계해석
		- 관계 데이터의 연산 표현하는 방법
		- 질의어로 표현, 비절차적 특성
		- 종류
			- 튜플 관계해석
			- 도메인 관계해석

8. 정규화 (Normalization)
	- 종속성 이론 이용해 잘못 설계된 스키마를 작게 쪼개 바람직한 스키마로 만드는 과정
	- 논리적 설계 단계에서 수행
	- 데이터 구조의 안정성 및 무결성 유지
	- 이상(Anomaly) 발생 방지 및 자료 저장 공간 최소화
		- 이상
			- 데이터들이 불필요하게 중복되어 예기치 못한 현상 발생
			- 종류
				- 삽입 이상 (Insertion Anomaly)
					- 데이터를 삽입할 때 원하지 않는 값들 함께 삽입
				- 삭제 이상 (Deletion Anomaly)
					- 한 튜플을 삭제할 때 상관없는 값들 함께 삭제
				- 갱신 이상 (Update Anomaly)
					- 일부 튜플만 갱신되어 정보에 모순 발생
	- 원칙
		- 정보의 무손실 표현
			- 한 스키마를 다른 스키마로 변환할 때 정보의 손실 없어야
		- 분리의 원칙
			- 독립된 관계성은 독립된 릴레이션으로 분리시켜 표현해야
		- 데이터 중복성 감소
	- 과정
		1. 1NF (제 1정규형)
			- 모든 속성 값이 원자 값으로만 되어있는 정규형
		2. 2NF (제 2정규형)
			- 모든 속성이 기본키에 대해 완전 함수적 종속 만족하는 정규형
				- 완전 함수적 종속
					- 기본키의 부분집합이 결정자가 되어서는 안 됨
		3. 3NF (제 3정규형)
			- 기본키가 아닌 모든 속성이 기본키에 대해 이행적 종속을 없애도록 테이블 분리
				- 이행적 종속
					- A->B 이고 B->C일 때 A->C 만족하는 관계
		4. BCNF
			- 모든 결정자가 후보키가 되도록 테이블 분리








