---

layout: post
title:  "IROS2016 Shared Autonomy"
categories: shared-autonomy
tag: [robotics, shared-autonomy]

---

# IROS2016 Workshop & Tutorial [1]

## Shared Autonomy
- Autonomy 레벨의 구분
  - 서로 목표에 대해 협상이 가능한 정도의 인지능력이 완벽한 Autonomy
  - 목표만 알고 모든 시스템을 수행하는 Autonomy
  - Planning과 Control Signal이 입력 될 때 하위 목표들을 수행하는 Autonomy

- IROS2016 
  - Physical HRI(hand over, co-manipulation etc.)
  - 의료 로봇
  - 매니퓰레이션 플래닝
  - 데모를 통한 학습
  - Grasping

- 2016 IROS 수준
  - Planning과 Control Signal이 입력 될 때 하위 목표들을 수행하는 Autonomy
  - Unidirectional

## Adaptive Long-Term Autonomy
- 현재의 로봇 기술은 완전 자율적이기엔 사람의 도움이 필요한 경우가 거의 모든 경우의 반 정도라고 주장
- 로봇이 사람과 상호작용하면서 사람들이 주도적으로 로봇을 도와주는 상황이 발생

## Bio-Inspired Social Robot Learning in Home Scenarios [2]
- Motivation
  - 일상생활에 로봇이 사용됨
  - 해결해야하는 작은 문제가 많다
    - 인지행동 문제점(Perceptual Behavioral Problem)
      - 소셜 그리고 생체모방법으로 해결할 수 있다고 생각함
- Developmental Bootstrapping
  - 학습 효율 비교
    - 기존의 기계학습
      - 3500 클래스를 학습하기 위해선 2백만 데이터가 필요
    - 어린 아이가 개발방식(Developmental Manner)로 학습할 경우 더 작은 데이터 개수로 학습이 가능
      - 간단한 선에서부터 선들이 합쳐진 복잡한 새로운 문자를 조합하면서 학습을 진행함
  - 멀티플 타임스케일 rnn을 제안
    - 센서 모터로부터 들어오는 인풋을 빠르거나 느린 네트워크의 구조적 유동을 통해 높은 인지와 낮은 인지를 모방
    - Network Model
      - 제안 모델이 cnn에서 컨볼루션(Convolution)과 풀링(Pooling)하는 과정과 비슷한 메커니즘을 지녔기에 이를 적용하여 비디오에서 사람이 움직이는 패턴을 학습하는 방법을 제시
    - 학습과정에서 새로운 학습 데이터가 나왔을 때 더 높은 레벨의 인지에 영향을 미치면서 새로운 패턴의 움직임을 실험적으로 보임
    - 뇌 구조에서 발생하는 모터 액터(motor actor)에 영향을 미치는 메커니즘과 같으므로 이를 데몬스트레이트한다고 주장
    - 처음엔 피지컬 가이던스로 시작하지만 이미테이션/제스처 그리고 언어적인 인스트럭션에 까지 확장이 가능할 것이라고 기대
- Bootstrapping
  - 현재 로봇들은 정형화 된 환경에서는 굉장히 동작을 잘함
    - 그렇지 못한 환경에서는 제대로 동작하지 않는 경우가 발생
    - 이를 해결하기 위해 점점 시스템이나 로봇에 자율성이 추가되지만 현재 모든 시스템들의 공통점은 한가지 목표만 잘 하는 로봇들이라는 것
    - 홈 시나리오에서나 미래에 필요한 로봇은 일반적인 목적의 로봇
    - 센서리 모터 스킬과 인지 스킬이 모두 잘 갖춰진 로봇을 말함
  - 기계학습 법만으로는 해결하기가 어렵다고 발표자는 생각
    - 그래서 기계학습법으로 동작하는 것 뿐만 아니라 심볼을 배우는 방법(고전 ai 방법)이 필요하다고 생각
    - 그러나 기존 방법처럼 모든 것들을 심벌화 하기는 힘들다
    - 그래서 센서리 데이터의 경험을 통해 학습을 하자는 방법론이 있지만 너무 고차원적임
  - 따라서 발표자는
    - 행동유도성(Affordance)을 발견하고 이를 다른 상황에 적용하는 방법을 고안
    - 이러한 원시적인것(Primitive)들이 많이 만들어지게 되면 그들만의 관계가 생기고 플래닝이 가능해짐
    - 대상물들의 간의 프리미티브와 플래닝을 통해 예측 궤도가 생겼을 때 다른 물건들에 이를 모방 적용할 수 있는 기본 지식이 생성이 된다
    - 심벌의 생성 방법은 물건들과 상호작용한 결과들과 물건들의 심층적인 이미지를 통해 카테고리를 생성
    - 이러한 규칙들과 위에서 생성한 예측 궤도를 PDDL을 통해 규칙 언어를 만들게 되면 해당 데이터들에 대한 인공지능 제어 스크립트가 생성됨
    - 생성된 스크립트는 로봇에 적용이 되어 카테고리를 생성하고, 주어진 복잡한 명령을 안정성, 대상의 형태, 실행가능성으로 나눠 목적에 맞게 행동을 수행하는 것을 실험으로 증명함
- Cross modal
  - 로봇이 새로운 환경에서 어떻게 학습을 하는지 신경 학습(Neural Learning)을 통해 설명
    - 인지(Recognize)- 이해(Understand) - 행동(Act)하기 위해 신경 학습을 사용
  - 신경학습의 크로스 모달 인테그레이션은 상구(Superior Colliculus)에서 작용하는 방법과 동일하게 작동
    - 인풋 레이어에서는 각자의 모달의 입력을 받고 아웃풋 레이어에서는 융합된 정보가 출력
    - 이러한 프레임워크를 기반으로 순차적인 행동을 분류하는 방법이 중요함
    - 이는 이벤트를 감지하는데 필수적인 사항이기 때문임
  - 소리와 시각, 시각과 움직임 등 각 데이터에 따라 사용되는 모달 형태들은 다양하며 예를 들어 사람의 움직임에 관련해서 학습하기 위해선 심층 카메라로 입력 받은 스켈레톤 좌표와 움직임의 궤적을 클러스터링 하여 학습을 시도
    - 크로스 채널 네트워크를 기반하여 RGB이미지와 깊이 이미지의 융합을 통해 감정을 실시간으로 구분하는 연구를 진행 중
  - 사회적 언어 습득
    - 단어-오브젝트(Object)와 같은 크로스 모델러티(Cross-Modality)
    - 언어는 뇌에서 비전, 모터, 청각이 모두 관여하기 때문에 크로스 모달이라고 할 수 있다
    - 언어는 시간의존형 속성(Time Dependency)이 존재하기 때문에 크로스 모달 멀티플 타임스케일 순환형 신경망(Recurrent Neural Network)을 사용하여 높은 인지와 낮은 인지 사이에 바인딩을 보임
- 해당 모델로 오브젝트와 비전 오브젝트의 연결을 통한 상황 적응 가능한 음성 인식 기술을 개발





## References

[1](http://www.irobotnews.com/news/articleView.html?idxno=8863)

[2] IEEE Trans. cognitive and developmental systems: special isues on bio-inspired social robot learning in home scenarios



















