# 📊 네트워크 대시보드
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black) 
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white) 
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black) 
![Express.js](https://img.shields.io/badge/Express.js-000000?style=flat&logo=express&logoColor=white)
###
[![Front_End](https://img.shields.io/badge/FrontEnd-blue?style=for-the-badge)](https://github.com/PointToPointNet/Front-End) 
[![Back_End](https://img.shields.io/badge/BackEnd-green?style=for-the-badge)](https://github.com/PointToPointNet/Back-End)
## 개요
네트워크 대시보드는 서버들의 네트워크 상태를 실시간으로 모니터링하고 다양한 통계를 제공하는 웹 애플리케이션입니다. 사용자는 메인 페이지에서 전체 서버 상태를 한눈에 파악할 수 있으며, 개별 서버의 상세 정보 및 기간별 통계를 조회할 수 있습니다. 또한, OpenAI 기반의 챗봇을 활용하여 네트워크 및 서버 관련 질문을 할 수 있습니다.

## 주요 기능
### 실시간 서버 상태 확인
- 메모리, Swap 메모리, CPU, 디스크 사용량 확인
- 서버 응답 속도 표시

### 서버 상세 정보 제공
- 서버 런타임 표시
- 메모리, Swap 메모리, CPU, 디스크 사용량 표시
- 서버 응답 속도 표시
- 네트워크 전송 속도 (bps)
- 포트 사용량
- 사용 중인 포트
- 접속 중인 유저 수
- 각 서버 및 전체 서버 기간별 통계 확인

### 추가 기능
- OpenAI 기반 챗봇을 통한 네트워크 및 서버 관련 질문 지원

## 폴더 구조
### 1. `server` 폴더
- Linux 명령어를 사용하여 네트워크 및 시스템 정보를 수집합니다.
- 수집된 데이터를 사용하기 쉽게 가공하여 JSON 파일로 저장합니다.
- 주요 수집 데이터:
  - CPU 및 메모리 사용량
  - 네트워크 전송 속도 (bps)
  - 디스크 사용량
  - 현재 접속 중인 사용자 수
  - 접속 중인 포트 등
  
### 2. `db_init` 폴더
- 수집된 데이터를 데이터베이스에 저장하는 역할을 합니다.
- 로그 데이터를 관리하여 기간별 통계를 제공할 수 있도록 구성합니다.
- 사용 기술: MySQL

### 3. `src` 폴더
- Express를 이용해 API 라우팅을 구현합니다.
- 클라이언트(프론트엔드)와 통신하여 필요한 데이터를 제공합니다.
- 주요 API 기능:
  - 서버 상태 데이터 조회
  - 기간별 로그 데이터 제공
  - 챗봇과 통신

## 기술 스택
### 프론트엔드
- **프레임워크**: React, TypeScript
- **기능 라이브러리**: d3.js, OpenAI API

### 백엔드
- **프레임워크**: Express.js
- **데이터 수집**: Linux 명령어 (예: `top`, `df`, `netstat`, `ifconfig` 등)
- **데이터 저장**: JSON 파일, MySQL

## 설치 및 실행 방법
### 1. 프로젝트 클론
#### 프론트엔드
```sh
git clone https://github.com/PointToPointNet/Front-End/ [directory]
cd [directory]
```
#### 백엔드
```sh
git clone https://github.com/PointToPointNet/Back-End/ [directory]
cd [directory]
```

### 2. 패키지 설치
#### 프론트엔드
```sh
npm install
```
#### 백엔드
```sh
npm install
```

### 3. 데이터베이스 초기화 (백엔드)
```sh
node db_init/app.js
```

### 4. 서버 실행
#### 프론트엔드
```sh
npm run dev
```
#### 백엔드
```sh
npm start
```

## 사용 방법
1. 메인 페이지에서 전체 서버 상태를 확인합니다.
2. 특정 서버를 클릭하여 상세 정보를 조회합니다.
3. 기간별 통계를 확인하고 분석합니다.
4. 챗봇을 활용하여 네트워크 및 서버 관련 질문을 합니다.
