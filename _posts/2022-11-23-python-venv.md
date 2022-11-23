---
layout: post
title:  "python virtual env"
categories: python-env
tag: [python, virtual, env]
---


### [Python] 가상 환경

- ### [Python] 가상환경 생성, 활성화, 비활성화, 삭제 방법(venv 활용)

  - https://heytech.tistory.com/295

  - 가상환경 생성
    - python -m venv 가상환경이름
    - (결과) 생성한 가상환경 이름으로 폴더 생성됨
  - 가상환경 활성화
    - source 가상환경이름/bin/activate
    - (결과) 현재 디렉토리 맨 앞에 가상환경 이름이 출력됨
  - 가상환경 비활성화
    - deactivate
  - 가상환경 삭제
    - sudo rm -rf 가상환경이름

- ### [Python] 가상환경 내 패키지 설치 및 관리 방법(venv 활용)

  - https://heytech.tistory.com/296
  - 패키지 설치
    - pip install 패키지이름
  - 설치된 패키지 리스트 저장
    - 패키지 목록 확인
      - pip list
    - 가상환경에 설치된 모든 패키지 리스트를 requirements.txt 파일에 저장
      - pip freeze > requirements.txt
  - 패키지 일괄 설치
    - pip install -r requirements.txt



### [Python] 환경 설정 (Vscode, Mac)

- https://jiaaan90.tistory.com/143

- Mac에 기본적으로 python 2.x가 설치됨
- Mac 자체에서 python 2.x를 사용하는 프로그램이 있으니 global 하게 설치는 하지 않는게 좋다
- 



### [Python] 아나콘다 가상환경

- https://dev-woody.tistory.com/7



### Pytorch 1.4.0 설치

- https://varhowto.com/install-pytorch-1-4-0/





### torchdata install

- https://github.com/pytorch/data#installation
- python -m venv torchdata-env
- source torchdata-env/bin/activate