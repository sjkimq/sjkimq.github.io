



---

layout: post
title:  "양자세계의 이해"
categories: quantum computing
tag: [quantum computing]

---





# 양자세계의 이해

## 양자물리의 핵심

- 세상의 모든 물질은 입자와 파동의 성질을 동시에 갖는다.
  - 이중슬릿 실험
    - 빛
    - 전자

- 중첩 (Superposition)
  - 물체 한 개가 가질 수 있는 여러 '상태'의 중첩을 의미
- 측정 (Measurement)
  - 측정하면 상태가 변화한다.
    - 양자물리는 물체의 상태가 중첩되어 있다가 우리가 관찰하는 순간 중첩이 사라진다고 말함
    - 측정 전에 중첩되어 있던 여러 상태는 측정되는 순간 하나를 제외하고 모두 사라짐
    - 하나를 제외하고 나머지 상태들이 모두 사라지는 현상을 ''붕괴'한다고 표현함
  - 고유 상태 : 측정 후 나타나는 상태
  - 중첩 상태 : 여러 고유 상태들이 중첩된 상태
  - 중첩된 상태를 측정하면 고유 상태 중 하나로 붕괴하므로 양자 세계의 물체들은 고유 상태에 있거나 중첩 상태에 있음 

- 얽힘 (Entanglement)
  - 두 개의 입자가 독립적이지 않고, 상대의 측정 결과에 영향을 받을 때



## 양자 물리의 기본 체계

- 양자 물리의 기본틀로 인정 - 1972년 솔베이 '제 5차 세계 물리학회'
  - 물질은 입자와 파동의 성질을 동시에 갖는다.
  - 물질은 중첩상태 또는 고유상태에 있다.
  - 중첩된 상태를 측정하면 하나의 고유상태만 남고, 나머지는 모두 붕괴되어 사라진다. 즉, 측정 행위는 상태를 변화시킨다.
  - 어느 고유상태가 남을지는 무작위로 결정된다.
  - 한 고유상태가 측정될 확률은 각 고유상태에 해당하는 물질파(입자 자체의 파동성을 나타내는 파동)의 진폭의 제곱에 비례한다.

## 양자정보기술의 탄생과 발전

- 1980년 : 폴 베니오프 양자컴퓨터 개념 제시
- 1982년 : 리처드 파인만 양자컴퓨터 필요성 주장
- 1984년 : 찰스 베넷, 질 브라사르 양자암호 통신 개념 제안
- 1993년 : 베넷의 양자원격이동 기술(물질 자체를 원격이동 시키는 것이 아닌, 물질의 정보를 이동시킴)
- 1994년 : 피터 쇼어의 공개키 암호 해독이 가능한 양자 알고리즘
- 1996년 : 로브 그로버의 데이터 검색 알고리즘
- 1997년 : 핵자기공명으로 양자컴퓨터 최초 구현 (2Qubit)
- 2010년 : 20Qubit 양자 컴퓨터
- 2020년 : 70Qubit 양자 컴퓨터
- 2022년 : 443Qubit 양자 컴퓨터(IBM)

## 양자컴퓨터의 기본연산

- 고전 컴퓨터의 기본 연산
  - 기본게이트 : AND, OR, NOT, XOR etc.

- 양자 컴퓨터의 기본 연산
  - 양자컴퓨터는 회전연산 + CNOT연산을 조합하여 모든 연산을 수행한다.
    - 회전연산
      - 두 개의 고유상태를 가진 모든 양자계를 큐비트로 사용 가능 (eg. spin-up, spin-down)
      - 입력신호 한 개, 출력신호도 한 개 (단일 큐빗 연산자)
    - CNOT연산
      - 두 입력 큐빗 중 한 큐빗의 상태에 따라 나머지 큐빗의 상태를 바꾸거나 그대로 두는 연산
      - 첫 번째 비트를 제어비트, 두 번째 비트를 표적비트
      - 제어비트는 그대로 통과
      - 표적비트는는 제어비트가 1일때 NOT 연산됨
      - 중첩상태에 NOT 이 가해지면, 각각의 고유상태에 NOT을 가한 후 중첩한 것과 같다.

## 양자컴퓨터의 하드웨어와 소프트웨어

- 양자 컴퓨터의 하드웨어
  - 큐빗이 있어야함
    - 물리량의 고유상태를 두 개 이상 가지고 있는 어떤 양자계나 가능
    - 읽기, 쓰기가 가능해야 한다.
    - 큐빗 간의 상호작용이 있어야 한다.
    - 결맞음 시간(Coherence Time : 1과 0이 그대로 유지되는 시간)이 길어야 한다.
  - 후보군
    - 공진기, 양자점, 초전도, 이온트랩, 핵자기공명, 스핀 등
- 핵자기공명 양자컴퓨터
  - 자기장을 이용해 스핀의 방향을 돌리는 기술, 결맞음 시간이 길다.
  - 초기에 2Q 양자컴퓨터를 먼저 만들었지만, 큐빗 수 확장이 어려워 개발이 더딘 상태
- 초전도체 양자컴퓨터
  - 2020년 70Q 개발
  - 영하 269도에서 동작
  - 저항이 0이 되면 초전도 전선을 고리 모양으로 만들고, 전선에 전류를 한 번만 흘려주면 전류가 없어지지 않고 계속 혼자서 공진.
  - 전류의 방향이 바뀌면 자기장의 방향이 바뀌므로 두 자기장의 방향을 큐빗의 0과 1로 사용
- 이온트랩
  - 이온 : 원자에서 전자가 하나 둘 더 붙거나, 떨어져 나간 상태
  - 공중에 이온을 잡아 놓아 이온들 하나 하나에 레이저를 쏘아 상태를 조절하는 방법
  - 이론이 큐빗의 역할, 레이저로 회전 연산을 수행
- 양자 컴퓨터의 소프트웨어
  - 중첩된 상태에 연산을 하면 각 고유상태에 개별적으로 연산이 가해짐
  - 01 ,10 중첩 상태에 첫 번째 큐빗에만 NOT 연산을 가해주면 11, 00 중첩 상태가 됨

## 양자기술의 현재

- 양자전산의 역사에서 가장 중요한 사건
  - 1994년 쇼어의 소인수분해 알고리즘
  - 1997년 핵자기공명 양자컴퓨터 구현
- 핵자기공명 양자컴퓨터 10Q 까지 개발 되었으나 큐빗 확장에 어려움
  - 이온트랩 방식이 대안으로 나옴
    - 2010년 20Q 개발
- D-wave의 양자컴퓨터
  - 게이트기반 범용 양자컴퓨터가 아님
  - '어닐링'기반이며 특정 종류의 문제만을 풀수 있음
- 2011년 캐나다 D-wave에서 128Q 초전도 양자컴퓨터 개발
- 2013년 D-wave 256Q 양자컴퓨터 개발
- 2019년 구글이 '양자우위' 논문 발표
- 양자컴퓨터 개발에서 큰 걸림돌 중 하나가 '오류수정'





















