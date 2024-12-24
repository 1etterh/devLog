---
tags:
  - git
draft: true
description:
---
## Outline
> 보안적 측면을 위해 Github API For Java를 활용하여 백엔드에서 Github RestAPI와 통신하고자 함.
> Github App을 만들고, 비밀 키는 백엔드 폴더에 로컬로 저장하였음
> 


## 새로 알게 된 점
1. JWT 토큰은 설치에 대한 정보를 요청할 때 사용한다.
2. Installation Token은 설치자의 조직에 접근할 때 사용한다.

### 해결을 위한 노력
1. 토큰만 백엔드에서 발급 후 그 외의 정보는 공식 API인 oktokit을 활용하였음.