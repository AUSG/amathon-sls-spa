# Amathon Pre-session: SPA Deployment using Serverless Framework

Amathon에 참가 신청해주신 여러분께 진심으로 환영한다는 인사부터 드립니다. 오늘 진행 할 실습 세션은 아마톤을 진행하기에 앞서 진행되는 워크샵입니다. 크게 깊은 내용은 아니지만, 행사 본래 취지에 맞게 초보자 분들도 AWS에 대한 이해를 조금 더 가져가셨으면 하는 마음에 준비했습니다.



### 본 세션의 학습 목표는 다음과 같습니다

- IAM를 이해한다

- S3, Lambda, API Gateway를 이해한다.

- [Serverless Framework](https://serverless.com)을 이용해 IaC(Insfrastructure as Code)를 체험해본다.

- 완성된 [Vue.js](https://vuejs.org) Application을 간단히 배포해본다.

  > 본 프로젝트에서는 SPA로 Vue.js를 예를 들어 실습을 진행합니다. React 환경에서도 몇가지 설정을 통하면 동일하게 배포 가능합니다.



# 필수 준비 사항



## 0. 본 Github Repository를 Download 해주세요!

중간중간 실습 파일들이 업로드 되어있습니다. 세션 시작 전 미리 다운 받아주세요! [다운로드](https://github.com/jeehyukwon/amathon-sls-spa/archive/master.zip)



## 1. PC 또는 Mac

본 세션은 코딩 과정이 포함되어 있습니다. 또한 CLI(Command Line Interface) 조작이 꼭 필요합니다. 모바일 환경(iPhone, iPad, Android)에서는 진행이 불가능하니 꼭 PC/Mac 환경에서 진행하세요.

> 본 실습 워크숍은 UNIX 환경을 전제로 하고 있습니다. Windows 사용자께서는 실습전 Linux를 설치하시거나 Cloud9등 Virtual Workspace 이용을 권장드립니다.



## 2. AWS 계정

- AWS 계정 만들기 [이동](https://aws.amazon.com/ko/)

본 가이드는 한명이 하나의 AWS 계정을 사용한다고 가정합니다. AWS IAM, S3, API Gateway, Lambda에 접근할 수 있어야 하며, 다른 사람과 계정을 공유하게되면 특정 리소스에 대해 충돌이 발생하므로 권장하지 않습니다.

본 워크샵의 일환으로 시작하는 모든 리소스는 AWS 계정이 12개월 미만인 경우, 제공하는 AWS 프리티어를 통해 충분히 무료 범위 내에서 실습 가능합니다. 만약 프리티어를 넘어서는 경우, 과금 될 수도 있습니다. 따라서, 새로운 실습용 계정을 만드시길 권장합니다. 자세한 내용은 [AWS 프리 티어 페이지](https://aws.amazon.com/free/)를 참조하세요.



## 3. 웹 브라우저

- Chrome 최신 버전 [다운로드](https://www.google.com/chrome/)
- Firefox 최신 버전 [다운로드](https://www.mozilla.org/ko/firefox/new/)

둘 중 원하시는 브라우저를 설치해주세요. 

> Internet Explorer는 AWS Web Console에서 문제가 발생 할 수 있습니다.



## 4. 텍스트 에디터

- VS Code [다운로드](https://code.visualstudio.com/)
- Atom [다운로드](https://atom.io/)

본 실습 세션에는 실제 코딩이 포함됩니다. 다음 둘 중 하나를 선택해서 꼭 설치해주세요.



## 5. Node.js

- Node.js 최신 버전 [다운로드](https://nodejs.org/en/)

[npm](https://www.npmjs.com/)을 사용하시려면 반드시 설치하셔야합니다. 겁먹지마세요!



# 자 그럼 이제 시작해볼까요?

1. 오늘 만들어 볼 Architecture에 대하여...
2. IAM에서 유저 생성하기
3. Vue-cli 3(@vue/cli)를 통해 새로운 Vue.js 앱 생성하기
4. Serverless Framework과 각종 플러그인 설치, serverless.yml 작성하기
5. CLI를 사용하여 쉽게 배포하기
6. CLI를 사용하여 쉽게 삭제하기