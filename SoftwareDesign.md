# Software Design

1. 요구사항 확인  
2. 화면 설계  
3. 어플리케이션 설계  
4. 인터페이스 설계  
----

## 1. 요구사항 확인
1. 소프트웨어 생명주기
	- 소프트웨어 생명주기: 소프트웨어를 개발하기 위한 과정을 각 단계별로 나눈 것
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
	- Scrum: 럭비에서 서로 대치해있는 대형 의미, 팀이 중심이 되어 개발의 효율성 높임
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











