# blockchain

블록체인 학습 코드와 경매 서비스 프로젝트를 함께 포함한 통합 저장소.

## 구성

- bc-practical-codes: Solidity, Hyperledger Fabric 실습 코드
- eth-explorer: 이더리움 블록/트랜잭션 조회 UI 샘플
- haribo-backend: 블록체인 기반 경매 서비스 백엔드
- haribo-frontend: 블록체인 기반 경매 서비스 프론트엔드

## 프로젝트 성격

- 단일 애플리케이션 저장소가 아닌 멀티 프로젝트 워크스페이스
- 교육/실습 코드와 서비스 코드가 혼재된 구조

## haribo-backend 요약

- Stack: Spring Boot 2, Java 8, Maven, JDBC(MySQL), web3j, Fabric Java SDK
- Domain: Member, Wallet, DigitalWork, Auction, Bid, Transaction
- API 범주:
  - 회원: 가입, 로그인, 조회, 수정, 삭제
  - 지갑: 등록, 조회, 소유자 조회, 충전
  - 작품: 등록, 조회, 수정, 삭제, 사용자별 조회, 이력 조회
  - 경매: 생성, 목록, 상세, 입찰, 취소, 종료, 사용자별 조회
  - 체인 조회: 블록, 트랜잭션, 주소, 경매 컨트랙트 조회

## haribo-frontend 요약

- Stack: Vue Router, web3, jQuery, Bootstrap
- 화면 범주:
  - 인증: 로그인, 회원가입
  - 마이페이지: 지갑, 작품, 회원정보
  - 작품: 등록, 상세, 수정, 사용자별 조회
  - 경매: 등록, 상세, 입찰
  - 익스플로러: 블록, 트랜잭션, 경매 조회

## 실행

### 사전 준비

- Java 8
- Maven 또는 mvnw
- MySQL
- 이더리움 노드 엔드포인트
- (선택) Hyperledger Fabric 네트워크

### 백엔드

1. haribo-backend/src/main/resources/application.properties 환경값 수정
2. 실행

```bash
cd haribo-backend
mvnw.cmd spring-boot:run
```

기본 포트: 8080

### 프론트엔드

```bash
cd haribo-frontend
python -m http.server 5500
```

접속: http://localhost:5500

## 운영 전 점검

- DB 주소/계정/비밀번호
- 이더리움 노드 주소
- 컨트랙트 주소 및 ABI 상수
- Fabric CA/Peer/Orderer 연결 정보
