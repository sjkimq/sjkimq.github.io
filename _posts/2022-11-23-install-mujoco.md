---
layout: post
title:  "Install MuJoCo"
categories: mujoco
tag: [mujoco]
---


# Install MuJoCo


## Mujoco 2.1.0 + mujoco-py 설치 [1], [2]
- Mujoco 2.1.0 다운로드 후 설치
  - https://mujoco.org/download/mujoco210-macos-x86_64.tar.gz 파일 다운로드
  - `mujoco210-macos-x86_64.tar.gz` 파일 압축 해제 $\rightarrow$ mujoco210 폴더 생성
  - ~/.mujoco 숨김 폴더 생성 후 `mujoco210` 폴더를 .mujoco 하위에 복사
    ```
    $ mkdir ~/.mujoco
    $ cp -r ./mujoco210 ~/.mujoco
    ```
- Mujoco 시뮬레이터 데모 실행해 보기
  - bin 디렉토리 안에 있는 simulate 실행 파일을 실행
    ```
    $ cd ~/.mujoco/mujoco210/bin
    $ ./simulate ../model/humanoid.xml​
    ```
- mujoco-py 설치
  - https://github.com/openai/mujoco-py 참고
    ```
    $ pip3 install -U 'mujoco-py<2.2,>=2.1'
    ```


## Mujoco 2.3.0 설치
- Mujoco 2.3.0 다운로드 후 설치
  - https://mujoco.org $\rightarrow$ Download 이동
  - `mujoco-2.3.0-macos-universal2.dmg` 파일 다운로드 후 실행
  - /Volumes/MuJoCo 에 마운트 됨
    ```
    $ ls /Volumes/MuJoCo
    MuJoCo.app          model               sample
    THIRD_PARTY_NOTICES mujoco.framework    simulate
    ```
  - ~/.mujoco 숨김 폴더 생성 후 파일 복사
    - .mujoco 숨김 폴더를 만들고 해제된 바이너리 파일을 .mujoco 폴더로 복사
      ```
      $ mkdir ~/.mujoco
      $ cp -r /Volumes/MuJoCo/ ~/.mujoco
      $ ls
      MuJoCo.app          model               sample
      THIRD_PARTY_NOTICES mujoco.framework    simulate
      $
      ```





## References
[1] [Let's do MuJoCo - 1.1 Mujoco, mujoco-py 설치](https://ropiens.tistory.com/169)

[2] [Let's do MuJoCo - 1.2 Mujoco 2.1.1 설치 및 mujoco-py 사용 방법](https://ropiens.tistory.com/178)

[3] [https://mujoco.org](https://mujoco.org)

[4] [https://github.com/deepmind/mujoco](https://github.com/deepmind/mujoco)

[5] [mujoco 설치하기](https://jdj2261.github.io/simulator/2021/10/02/mujoco-install.html)

