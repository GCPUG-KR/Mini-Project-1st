# AutoML Tables

## 컨트리뷰터
- 이용운(Roy Lee) yongwoonyo@gmail.com

## 인트로
2018년 샌프란시스코에서 열린 Google NEXT에 참가했을 때 AutoML을 처음 접했는데 굉장히 인상적이었던 기억이 있다.
그런데 불과 2년 남짓 지났을까 .. AutoML 하위 서비스들이 줄줄이 비엔나로 쏟아져 나오고, 발전하고 있어서 다시 한번 놀랐다.

### AutoML 하위 서비스들
2020-06 기준, 사용 가능한 AutoML 하위 서비스들을 읊어보자면 
- AutoML Vision
- AutoML Video Intelligence
- AutoML Natural Language
- AutoML Translation
- AutoML Tables
가 존재한다.

이 중 AutoML Tables에 대해 살펴보려고 한다.

### AutoML Tables이 다르게 느껴지는 부분?
AutoML 하위 서비스들 가운데 AutoML Tables는 약간 색깔이 다르다. AutoML 하위 서비스들 가운데 AutoML Tables가 아닌 것들은 OCR 인식, 비디오 장면 전환, 오브젝트 트래킹, 자연어 처리, 언어 감지 및 번역 등 그 자체로 프로덕트의 메인 기능이 되는 성격이라고 할 수 있다. 그런데 AutoML Tables는 구조화된 데이터만 있다면 그 데이터로 Machine Learning Model을 학습시키고 예측하게 하는, 개인적으로 느끼기엔 AI Platform (구 Cloud Machine Learning Engine, CMLE) 을 더 사용하기 쉽게 추상화시킨 서비스처럼 다가온다.
어떤 부분 때문에 그렇게 느끼냐면, AI Platform의 경우 Machine Learning Model을 학습시키고 관리하기 위해서는 gcloud SDK 커맨드를 쉘 스크립트로 작성해줘야 하는 등 번거로움이 있었는데 이 과정이 개선되었다고 느낀다.
하지만 AI Platform에 비해 모델 선택, 파라미터 조정 등 모델을 만들어 가는 과정에서 다방면으로 느껴지는 자유도는 아쉬운 것이 사실이다.

### 삼천포로 살짝 빠져보자면
필자는 인하우스 머신 또는 클라우드 VM에 환경을 설치해서 ML을 하다가 GCP CMLE가 출시되고나서 부터는 CMLE만 주구장창 사용해왔다. 여전히 비즈니스에 최적화된 머신러닝 모델을 만들고 운영하기에는 CMLE (현 AI Platform)가 최고라고 생각되지만 버짓을 생각하면 다른 선택을 해야 할 수도 있겠다고 느낀다. 팀빌딩을 할 때 예산이 어느 정도 되느냐에 따라 시니어와 주니어의 비율을 다르게 구성하게 된다. 데이터 사이언티스트 역시 레벨이 여럿으로 나뉘는데 예산이 부족해서 기본적인 이론은 깨우쳤으나 서비스를 프로덕션으로 올리기 어려운 사람들을 채용해야 하는 경우, 또는 데이터 사이언티스트를 여러 명을 채용하지 못해서 소수의 인원이 여러 AI 프로덕트를 단기간 내에 개발해야 하는 경우에는 어느 정도 자동화를 지원하는 서비스를 택하는 것이 좋을 것이다. 적어도 이런 경우에 대해서는 AutoML Tables이 최선의 선택이 아닐까 싶다.

썰이 길었다.
본격적으로 AutoML Tables를 살펴보자.

