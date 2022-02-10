# Software Design

1. 요구사항 확인  
2. 화면 설계  
3. 어플리케이션 설계  
4. 인터페이스 설계  
----

## 1. 요구사항 확인
1. 소프트웨어 생명주기
	- 소프트웨어를 개발하기 위한 과정을 각 단계별로 나눈 것
	- 소프트웨어 생명 주기 모형
		- Waterfall Model (폭포수 모형)  
			![image](https://user-images.githubusercontent.com/53277342/153363657-db248743-2bb2-40bf-b7ce-c5f6c60bdcf6.png)
			- 각 단계를 확실히 매듭짓고 다음 단계를 진행하는 개발 방법론
			- 선형 순차적 모형
			- 고전적 생명 주기 모형
			
		- Prototype Model (프로토타입 모형)  
			![image](https://user-images.githubusercontent.com/53277342/153363804-4ad3fba7-6baa-44e2-8858-2736cdd56d56.png)
			- 실제 개발될 소프트웨어에 대한 견본(프로토타입)을 만들어 최종 결과물 예측
		
		- Spiral Model (나선형 모형, 점진적 모형)  
			![image](https://user-images.githubusercontent.com/53277342/153364058-a9138cef-7e66-491d-b9f4-aa2d2b11c067.png)
			- 폭포수 모형 + 프로토타입 모형 + 위험 분석 기능
			- 여러 번의 개발 과정을 거쳐 점진적으로 완벽한 소프트웨어 개발
			- 유지보수 과정 필요 없음
			- 위험 관리, 위험 최소화 목적
		
		- Agile Model (애자일 모형)  
			- 일정한 주기(Sprint, Iteration)를 반복하면서 개발과정 진행
			- 고객과의 소통에 초점을 맞춘 방법론
			- 급변하는 요구사항에 적합
			- ex) Scrum, XP, Kanban, ASD, FDD(Feature Driven Development, 기능중심개발)

2. Scrum 기법
	- 럭비에서 서로 대치해있는 대형 의미, 팀이 중심이 되어 개발의 효율성 높임
	- 팀 구성
		- PO (Product Owner, 제품 책임자)  
			- 요구사항 작성 주체, 주로 개발 의뢰자나 사용자가 담당
			- Backlog 작성, 우선순위 지정
			- 주기적으로 요구사항 우선순위 갱신
		- SM (Scrum Master, 스크럼 마스터)  
			- 스크럼을 잘 수행할 수 있도록 조언해주는 가이드 역할
			- 일일 스크럼 회의 주관, 진행사항 점검, 장애요소 공론화 및 처리
		- DT (Development Team, 개발팀)   
			- PO와 SM을 제외한 모든 팀원
			- 개발자 외에도 개발에 참여하는 모든 사람이 대상
	- 개발 프로세스
		1. Product Backlog (제품 백로그)  
			- 제품 개발에 필요한 모든 요구사항을 우선순위에 따라 나열한 목록
			- 지속적 업데이트
			- 릴리즈 계획 수립
		2. Sprint Planning Meeting (스프린트 계획 회의)  
			- 단기 일정 수립
			- 요구사항을 Task 작업 단위로 분할 후 Sprint Backlog 작성
		3. Sprint
			- 실제 개발 작업 진행
			- To Do(할 일), In Progress(진행 중), Done(완료)의 상태 가짐
			- Daily Scrum Meeting (일일 스크럼 회의)
				- 매일 15분정도의 짧은 시간동안 진행상황 점검
				- 남은 작업 시간 Burn-down Chart(소멸차트)에 표시
		4. Sprint Review (스프린트 검토 회의)
			- 요구사항에 잘 부합되는지 사용자 앞에서 테스팅 수행
			- PO는 개선할 사항에 대해 피드백 정리, Product Backlog 업데이트
		5. Sprint Retrospective (스프린트 회고)
			- 스프린트 주기 되돌아보며 규칙 잘 준수했는지, 개선할 점 확인 및 기록

3. XP(eXtreme Programming) 기법  
	- 고객의 참여와 개발과정의 반복 극대화해 개발 생산성 향상시키는 방법
		- 짧고 반복적인 개발 주기, 단순한 설계, 고객의 적극적 참여
		- 소프트웨어를 빠르게 개발하는 것을 목적
	- 핵심 가치
		- Communication(의사소통)
		- Simplicity(단순성)
		- Courage(용기)
		- Respect(존중)
		- Feedback(피드백)
	- 개발 프로세스  
	![image](https://user-images.githubusercontent.com/53277342/153368805-a7142f73-e107-40c7-942e-3ee59caff769.png)
		1. User Story (사용자 스토리)
			- 고객의 요구사항을 간단한 시나리오로 표현
			- 기능 단위로 구성, 테스트 사항 기재
		2. Release Planning (릴리즈 계획 수립)
			- 릴리즈: 부분적으로 기능이 완료된 제품을 제공하는 것
		3. Spike (스파이크)
			- 신뢰성 향상, 위험 감소하기 위해 별도로 만든 간단한 프로그램
			- 처리할 문제 외의 조건은 모두 무시하고 작성
		4. Iteration (이터레이션)
			- 하나의 릴리즈를 더 세분화한 단위
			- 1~3주 정도의 기간으로 진행
			- 기간 중에 새로운 스토리 작성 가능
		5. Acceptation Test (승인 검사, 인수 테스트)
			- 릴리즈 단위 부분 완료 제품 구현되면 수행하는 테스트
			- 사용자 스토리 작성 시 기재한 테스트 사항에 대해 고객이 직접 수행
			- 발견한 오류 사항은 다음 이터레이션에 포함
			- 새로운 요구사항 작성, 상대적 우선순위 변경 가능
		6. Small Release (소규모 릴리즈)
			- 소규모의 경우 고객의 반응 기능별로 확인 가능, 요구사항 유연히 대응 가능
			- 이터레이션이 모두 완료되면 고객에 의한 최종 테스트 수행, 고객 전달
	- 주요 실천 방법
		- Pair Programming (짝 프로그래밍)
			- 개발에 대한 책임 공동 소유
		- Collective Ownership (공동 코드 소유)
			- 개발 코드에 관한 권한과 책임 공동 소유
		- Test-Driven Development (테스트 주도 개발)
			- 개발자가 테스트케이스 먼저 작성하여 무엇을 해야할지 정확히 파악
			- 자동화된 테스팅 도구 사용
		- Whole Team (전체 팀)
			- 모든 구성원들은 각자 자신의 역할을 가지며 역할에 대한 책임 가짐
		- Continous Integration (CI, 계속적인 통합)
			- 하나의 작업 마무리될 때마다 모듈 단위로 나눠 개발된 코드들 지속적 통합
		- Design Improvement (= Refactoring, 디자인개선)
			- 프로그램 기능 변경 없이 단순화, 유연성 강화 통해 시스템 재구성
		- Small Releases (소규모 릴리즈)
			- 릴리즈 기간 짧게 반복해 고객의 요구 변화에 신속히 대응

4. 현행 시스템 파악
	- 새로 개발하려는 시스템의 개발 범위 명확히 설정 목표
	- 파악 절차
		1. 1단계
			1. 시스템 구성 파악
				- 기간 업무, 지원 업무 구분하여 기술
					- 기간 업무: 조직의 주요 담당 업무
					- 지원 업무: 담당 업무를 지원하기 위한 업무
			2. 시스템 기능 파악
				- 단위 업무 시스템이 현재 제공하는 기능들을 주요기능 - 세부기능으로 구분
			3. 시스템 인터페이스 파악
				- 단위 업무 시스템간 주고받는 데이터 정보 명시
					- 데이터의 종류, 형식, 프로토콜, 연계 유형, 주기
		2. 2단계
			1. 아키텍처 구성 파악
				- 기간 업무 수행에 어떤 기술 요소들 사용되는지 아키텍처 구성도 작성
			2. 소프트웨어 구성 파악
				- 단위 업무 시스템별로 설치되어 있는 소프트웨어의 정보 명시
					- 소프트웨어 제품명, 용도, 라이센스 적용 방식, 라이센스 수
		3. 3단계
			1. 하드웨어 구성 파악
				- 단위 업무 시스템들이 운용되는 서버의 정보 명시
					- 서버 주요 사양, 수량, 이중화 적용 여부
						- 이중화(Replication): 운용 서버의 장애 시 대기 서버
			2. 네트워크 구성 파악
				- 서버의 위치, 서버간 네트워크 연결 방식을 네트워크 구성도로 작성

5. 개발 기술 환경 파악
	- 개발 기술 환경: 개발하고자 하는 소프트웨어와 관련된 요소의 고려사항 기술
		- 관련 요소
			- OS (Operation System, 운영체제)
				- 컴퓨터 시스템의 자원 편리하고 효율적으로 사용하도록 환경 제공하는 소프트웨어
				- 컴퓨터 사용자와 하드웨어간의 인터페이스
				- ex) Windows, UNIX, Linux, Mac OS, iOS, Android
				- 고려사항
					- 가용성, 성능, 기술 지원, 주변 기기, 구축 비용
			- DBMS (DataBase Management System, 데이터베이스 관리시스템)
				- 사용자의 요구에 따라 정보 생성, DB 관리해주는 소프트웨어
				- 데이터의 종속성과 중복성 문제 해결하기 위해 제안된 시스템
				- 모든 응용 프로그램들이 DB 공용할 수 있도록 관리
				- DB 구성, 접근 방법, 유지관리에 대한 모든 책임 가짐
				- ex) Oracle, MySQL, SQLite, MongoDB, Redis
				- 고려사항
					- 가용성, 성능, 기술 지원, 상호 호환성, 구축 비용
			- WAS (Web Application Server, 웹 어플리케이션 서버)
				- 동적 컨텐츠를 처리하기 위해 사용되는 미들웨어
				- 데이터 접근, 세션 관리, 트랜잭션 관리 위한 라이브러리 제공
				- 주로 DB 서버와 연동해서 사용
				- ex) Tomcat, JEUS, WebSphere
				- 고려사항
					- 가용성, 성능, 기술 지원, 구축 비용
			- Open Source
				- 누구나 별다른 제한 없이 사용할 수 있도록 소스코드 공개한 것
				- 고려사항
					- 라이선스 종류, 사용자 수, 기술의 지속 가능성
			
6. 요구사항 정의
	- 요구사항: 서비스에 대한 설명, 정상적으로 운영되는데 필요한 제약조건
	- 유형
		- Functional Requirements (기능 요구사항)
			- 시스템이 무엇을 하는지, 어떤 기능을 하는지
			- 입출력에 무엇이 포함되어야 하는지
			- 어떤 데이터를 저장하거나 연산을 수행해야 하는지
		- Non-functional Requirements (비기능 요구사항)
			- 시스템 장비 구성, 서능, 인터페이스, 데이터, 테스트, 보안, 품질, 관리, 지원 요구사항
		- User Requirements (사용자 요구사항)
			- 사용자 관점에서 제공해야할 요구사항
			- 친숙한 표현 사용
		- System Requirements (시스템 요구사항, 소프트웨어 요구사항)
			- 개발자 관점에서 제공해야할 요구사항
			- 전문적이고 기술적인 용어 사용
	- 개발 프로세스
		1. Requirement Elicitation (요구사항 도출, 수집)
			- 요구사항이 어디에 있는지, 어떻게 수집할 것인지 식별 및 이해
			- 효율적인 의사소통 중요
			- 기법: 인터뷰, 브레인스토밍, 프로토타이핑, 유스케이스
			
		2. Requirement Analysis (요구사항 분석)
			- 요구사항 중 명확하지 않아 이해되지 않는 부분 발견, 걸러내기 위한 과정
			- 타당성 조사, 비용 및 일정에 대한 제약 설정
			- 상충되는 요구사항 중재
			- 소프트웨어 범위 파악
			- 구조적 분석 기법
				- 자료의 흐름과 처리 중심 요구사항 분석 방법
				- 도형 중심의 도구 사용해 대화 용이
				- 하향식 방법 사용해 시스템 세분화, 분석 중복 배제
				- ex) DFD, DD, Mini-Spec., ERD, STD, 제어 명세서
					- DFD (Data Flow Diagram, 자료 흐름도, 자료 흐름도, 버블 차트)
						- 자료의 흐름 및 변환 과정, 기능을 도형 중심으로 기술하는 방법
						- 기호
							![image](https://user-images.githubusercontent.com/53277342/153383602-b6f1ca95-cfc9-4039-b530-648ef0f1d8e8.png)
							- Process(프로세스): 자료 변환시키는 부분
							- Data Flow(자료 흐름): 자료의 이동이나 연관관계
							- Data Store(자료 저장소): 시스템에서의 자료 저장소(파일, DB)
							- Terminator(단말): 시스템과 교신하는 외부 개체, 입력 데이터 생성, 출력 데이터 받음
					- DD (Data Dictionary, 자료 사전)
						- DFD에 있는 자료 더 자세히 정의, 기록
						- Meta Data: 데이터를 설명하는 데이터, 데이터의 데이터
						- 기호
							![image](https://user-images.githubusercontent.com/53277342/153393935-6edd7c8e-472e-4e69-bdbb-6c87b1989b87.png)		
			- CASE
				- 요구사항 자동 분석, 분석 명세서를 기술하도록 개발된 도구
				- 문서화 품질 개선, 명세에 대한 유지보수 비용 축소, 영향 추적의 용이성
				- 종류
					- SADT(Structured Analysis and Design Technique)
						- 시스템 분석, 요구사항 분석, 시스템 설계 위한 구조적 분석 및 설계 도구
						- 블록 다이어그램 채택
					- SREM(Software Requirements Engineering Methodology, RSL/REVS)
						- 실시간 처리 소프트웨어에서 요구사항 명확히 기술 목적
						- RSL, REVS 사용
							- RSL(Requirement Statement Language)
								- 요소, 속성, 관계, 구조 기술하는 요구사항 기술 언어
									- 요소: 요구사항 명세 개발 위해 사용되는 개체, 개념
									- 속성: 요소 수정, 수식
									- 관계: 개체들간의 관계
									- 구조: 정보 흐름 묘사
							- REVS(Requirement Engineering and Validation System)
								- RSL로 기술된 요구사항 자동 분석, 요구사항 분석 명세서 출력
					- PSL/PSA
						- PSL과 PSA 사용하는 자동화 도구
							- PSL(Problem Statement Langauage)
								- 요구사항 기술 언어
							- PSA(Problem Statement Analyzer)
								- PSL로 기술된 요구사항 자동 분석, 요구사항 분석 명세서 출력
					- TAGS(Technology for Automated Generation of Systems)
						- 시스템공학 방법 응용에 대한 자동 접근 방법
						- 개발 주기의 전 과정에 이용 가능한 통합 자동화 도구
						- IORL: 요구사항 명세 언어

			- HIPO(Hierarchy Input Process Output)
				- 시스템 분석, 설계, 문서화할 떄 사용되는 기법
				- 입력, 처리, 출력 기능 나타냄
				- 하향식 소프트웨어 개발 위한 문서화 도구
				- HIPO Chart: 시스템 기능을 여러 개의 모듈로 분할하여 모듈간의 인터페이스를 계층 구조로 표현
					- Visual Table of Contents(가시적 도표, 도식 목차): 시스템의 전체적 기능, 흐름 보여주는 계층 구조도
					- Overview Diagram(총체적 도표, 개요 도표): 프로그램 구성 기능 기술, 입력-처리-출력에 대한 정보 제공
					- Detail Diagram(세부적 도표, 상세 도표): 총체적 도표에 표시된 기능을 구성하는 기본 요소들 상세 기술

		3. Requirement Specification (요구사항 명세)
			- 분석된 요구사항 바탕으로 모델 작성, 문서화
			- 기능 요구사항: 빠짐없이 완전하고 명확하게 기술
			- 비기능 요구사항: 필요한 것만 명확하게 기술
			- Software Requirement Specification (소프트웨어 요구사항 명세서)
				- 소프트웨어가 반드시 제공해야 하는 기능, 특징, 제약조건 명시
				- 명세 기법
					- 정형 명세 기법
						- 수학적 원리, 모델 기반
						- 수학적 기호로 정형화된 표기법 사용
						- ex) VDM, Z, CSP
					- 비정형 명세 기법
						- 상태, 기능, 객체 중심
						- 자연어 기반 서술, 다이어그램 작성
						- ex) FSM, ER 모델링, Decision Table, State Chart(SADT)
		4. Requirement Validation (요구사항 확인, 검증)
			- 요구사항 명세서가 정확하고 완전하게 작성되었는지 검토

7. UML(Unified Modeling Language)
	- 시스템 개발 과정에서 의사소통이 원할하도록 표준화한 객체지향 모델링 언어
	- 구성 요소
		- Things(사물)
			- 관계가 형성될 수 있는 대상
			- Structural Things(구조 사물)
				- 시스템의 개념적, 물리적 요소 표현
				- ex) Class, Use Case, Component, Node
			- Behavioral Things(행동 사물)
				- 시간과 공간에 따른 요소들의 행위 표현
				- ex) Interaction(상호작용), State Machine(상태 머신)
			- Grouping Things(그룹 사물)
				- 요소들 그룹으로 묶어서 표현
				- ex) Package
			- Annotation Things(주해 사물)
				- 부가 설명, 제약조건 표현
				- ex) Note

		- Relationships(관계)
			- 사물간의 연관성 표현  
			  ![image](https://user-images.githubusercontent.com/53277342/153404287-6ee6d406-e879-48bd-9f4f-83ad708cb7fa.png)
			- Association(연관 관계)
				- 2개 이상의 사물이 서로 관련된 관계
				- 양방향 관계의 경우 화살표 생략
				- Multiplicity(다중도) 선 위에 표기
			- Aggregation(집합 관계)
				- 하나의 사물(Part)이 다른 사물(Whole)에 포함되어있는 관계
				- Part와 Whole은 서로 독립적
				- Part에서 Whole 쪽으로 속이 빈 마름모 향함
			- Composition(포함 관계)
				- 집합 관계의 특수한 형태, Whole의 변화가 Part에 영향을 미치는 관계
			- Generalization(일반화 관계, 상속)
				- 하나의 사물(Parent)이 다른 사물(Child)에 비해 더 일반적인 관계
				- Child에서 Parent 쪽으로 속이 빈 화살표 향함
			- Dependency(의존 관계)
				- 서로 포함관계가 아니고 사물의 변화가 다른 사물에 영향 미치는 관계
				- 영향을 주는 사물에서 영향을 받는 사물 쪽으로 점선 화살표 향함
			- Realization(실체화 관계, 인터페이스)
				- 사물이 할 수 있거나 해야하는 기능으로 서로 그룹화할 수 있는 관계
				- 사물에서 기능 쪽으로 속이 빈 점선 화살표 향함

		- Diagram
			- 사물과 관계를 도형으로 표현한 것
			- 여러 관점에서 시스템을 가시화한 View 제공
			- Structural Diagram
				- 주로 정적 모델링에서 사용
				- Class Diagram: 클래스 사이의 관계 표현
				- Object Diagram: 특정 시점의 객체간 관계 표현
				- Component Diagram: 컴포넌트간 관계 표현
				- Deployment Diagram: 물리적 요소들의 위치 표현
				- Composite Structure Diagram: 복합 구조 갖는 경우 내부 구조 표현
				- Package Diagram: 패키지들의 관계 표현
			- Behavioral Diagram
				- Use Case Diagram: 사용자의 요구 분석 위해 사용자와 사용사례로 구성
				- Sequence Diagram: 객체들이 주고받는 메시지 표현
				- Communication Diagram: 객체간 메시지 + 연관관계 표현
				- State Diagram: 속한 클래스의 상태 변화, 객체간 상호작용에 따른 변화 표현
				- Activity Diagram: 시스템의 처리 흐름을 순서에 따라 표현
				- Interation Overview Diagram: 상호작용 다이어그램간 제어흐름 표현
				- Timing Diagram: 객체 상태 변화, 시간 제약 명시적 표현
		
		- Stereotype
			- 기본 기능 외에 추가적 기능 표현
			- << >> (Guilemet, 길러멧) 사이에 표현할 형태 기술
				- include, extend, interface, exception, constructor






