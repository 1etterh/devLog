---
tags:
  - troubleshooting
  - githubapi
  - java
  - oktokit
---
### 문제
1. Backend: Spring Boot(Java)
2. API: GitHub API For Java

1. 보안을 위해 백엔드에서 Github의 데이터를 수신 후 프론트엔드에 전송하고자 함.
 2. Github Installation Token을 통해 프로젝트 리스트를 요청했으나 메소드가 Deprecated되어 동작하지 않음.
 3. Github API for Java만으로 문제를 해결하기에는 프로젝트 기한이 짧음
	 1. 직접 contribute하거나
	 2. 이슈 등록 후 해결되길 기다리기
	 3. -> 둘 다 기대하기 힘들다.

### 원인 분석
> GitHub API For Java는 개인이 배포한 오픈소스 API이며, deprecated된 method들이 존재함.
### 해결 방법
1. GitHub API For Java를 통해 JWT와 GitHub Installation Token을 생성하고 이를 통해 인증할 수 있음
2. Github 공식 API인 Oktokit(Javascript 기반)를 활용하여 필요한 데이터를 요청할 수 있음
3. 설치, 인증 및 권한 정보는 Backend에서 관리하며, 필요한 경우 프론트 엔드(VueJS)에서 Oktokit을 활용할 수 있음
4. 보안을 위해 Installation Token은 필요한 경우에 한하여 발급하며, 사용 후 일정 시간이 지나면 비활성화 할 수 있음

### 결과
1. oktokit과 GraphQL을 통해 필요한 data만 요청할 수 있음
2. GitHub 인증 정보는 backend에 저장하여 보안성을 최대한 확보

# refs
1. [GitHub API For Java](https://github-api.kohsuke.org/)
2. [Oktokit](https://github.com/octokit)
