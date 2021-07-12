# SK Happy Delivery

## 1. 분석/설계

### 이벤트스토밍

- url: http://www.msaez.io/#/storming/wf1WRjEyVVWd1Abldu2nsM6FwbL2/58c36eee763868e2a4b6cc1f019683fe


### 이벤트 도출

![이벤트도출결과](https://user-images.githubusercontent.com/45377807/125230473-ca215d00-e313-11eb-8866-2bdbfd5480be.png)




### 액터, 커맨드 부착
![액터 커맨드 부착](https://user-images.githubusercontent.com/45377807/125232032-c3e0b000-e316-11eb-8af4-cf98f7b97dac.png)
 

### 어그리게잇 묶기
![어그리게잇으로 묶기](https://user-images.githubusercontent.com/45377807/125232099-e7a3f600-e316-11eb-97ae-275b528205bd.png)


### 바운디드 컨텍스트 묶기
<img width="830" alt="바운디드컨텍스트 묶기" src="https://user-images.githubusercontent.com/45377807/125232137-f7bbd580-e316-11eb-82f0-293cd566faac.png">


### 폴리시 부착
<img width="828" alt="폴리시 추가" src="https://user-images.githubusercontent.com/45377807/125232200-16ba6780-e317-11eb-9e1d-db6cce330b92.png">


### 완성된 모형(실선은 Req/Res, 점선은 Pub/Sub)
<img width="830" alt="이벤트스토밍 결과" src="https://user-images.githubusercontent.com/45377807/125232289-423d5200-e317-11eb-83e9-f936ad5ea2c4.png">



### 헥사고날 아키텍처 다이어그램 도출
![헥사고날 아키텍쳐 다이어그램](https://user-images.githubusercontent.com/45377807/125233520-b7aa2200-e319-11eb-959d-6f60e25f1f75.png)


## 2. 구현

분석/설계단계에서 도출된 헥사고날 아키넥처에 따라, 각 바운디트 컨텍스트 별로 대변되는 마이크로 서비스들을 스푸링부트로 구현하였다. 구현한 각 서비스를 로컬에서 실행하는 방법은 아래와 같다

![메이븐 실행](https://user-images.githubusercontent.com/45377807/125234914-96970080-e31c-11eb-933b-7008c23038bf.png)


***(아래 부터 수정이 필요합니다.)***
### Domain Driven Design의 적용
각 서비스 내에 도출된 핵심 어그리게잇 객체를 엔티티로 선언했다. 이때 가능한 현업에서 사용하는 유비쿼터스 랭귀지를 사용하려 노력했다.
#### kafka 활용한 Pub/Sub 구조
#### Correlation Key
#### Scaling-out
#### 취소에 따른 보상 트랜젝션
#### CQRS
#### Message Consumer


엔티티 패턴과 레포지토리 패턴을 적용하여 JPA를 통한 다양한 데이터소스 유향에 대한 별도의 처리가 없도록 데이터 접근 어댑터를 자동 생성하기 위하여 Spring Data REST의 Repository를 적용했다.


### 적용 후 REST API의 테스트
![REST API테스트](https://user-images.githubusercontent.com/45377807/125235333-43717d80-e31d-11eb-87c8-e08e0edb2280.png)


### Polyglot Programming/Persistence
#### 
#### 
#### 



## 3. 운영

### SLA 준수
#### Pod생성 시 Liveness 와 Readiness Probe를 적용했는가?
#### 셀프힐링: Liveness Probe를 통해 일정 서비스 헬스 상태 저하에 따른 Pod 재생되는지 증명
#### 서킷브레이커 설정: 서킷브레이커 적용 + 리트라이 적용 + Pull Ejaction 적용
#### 오토스케일러(HPA)
#### 모니터링, 앨러팅
#### Stateless 한 구현?



### CI/CD 설정
#### AWS Code Build 적용됐는가?
#### Contract Test
#### (Advanced) Canary Deploy, Shadow Deply, A/B Test (각 2점)
                
### 운영 유연성
#### Config Map / Secret
