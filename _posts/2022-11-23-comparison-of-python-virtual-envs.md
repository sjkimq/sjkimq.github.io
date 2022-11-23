---
layout: post
title:  "comparison of python virtual environments"
categories: python-env
tag: [python, virtual, env]
---

## Summary
- pipenv
- venv
- docker
- conda (anaconda)
- pyenv-virtualenv
- virtualenv
- pyvenv


## pipenv
- 장점
  - pipfile.lock 파일을 기반으로 패키지 관리
    - lock 파일로 패키지 관리를 하면 다음과 같은 장점
      - virtualenv로 가상환경을 생성하면서 pip으로 패키지를 자동으로 설치
      - lock파일의 해쉬로 안전한 버전 관리가 가능
      - pip으로 패키지를 설치/추가하면 자동으로 pipfile에 변경사항이 반영
  - 파이썬에서 공식으로 권장하는 가상환경 모듈
- 사용법
  - pipenv 설치
    ```
    pip install pipenv
    ```
  - 가상환경 생성/제거
    - 가상환경 생성 시 원하는 파이썬 버전을 입력
      ```
      # 생성
      pipenv --python 3.X
      # 제거
      pipenv --rm
      ```
  - 가상환경 실행
    - `shell` 로 실행
      - 가상환경이 활성화된 터미널이 열림
        ```
        # Run shell
        pipenv shell
        ```
    - `run` 으로 실행
      - 스크립트 또는 명령어를 가상환경에서 실행만 하고 가상환경을 활성화하지는 않는 방법
        ```
        # Rum custom commands
        pipenv run COMMANDS...
        ```
  - 가상환경 종료
    - 가상환경을 종료하려면 해당 터미널을 빠져나온다
      ```
      exit
      ```
  - 패키지 관리


## venv
- 장점
  - 파이썬에 내장되어 있는 가상환경 모듈
  - Python 3.5 이후부터는 파이썬 표준 라이브러리에 들어가 있는 가상환경 생성 방법
  - `pip`이 내장되어 있어 매우 편리
- 가상환경 생성
  ```
  python3 -m venv ENV_NAME
  ```
- 가상환경 실행
  ```
  source ENV_NAME/bin/activate
  ```
- 가상환경 종료
  ```
  deactivate
  ```
- 패키지 관리
  - 패키지 관리는 pip과 requirements.txt로 한다
    ```
    # 설치
    pip3 install -r requirements.txt
    
    # Lock
    pip3 freeze > requirements.txt
    ```

- 참고
  - PyCharm에서 기본적으로 제공하는 가상환경  



## docker







## conda (anaconda)
- 특징
  - 머신러닝, 데이터과학 분야의 다양한 라이브러리들이 설치된 런타임인 아나콘다 파이썬에서 기본적으로 제공되는 가상환경 모듈
  - 굳이 아나콘다를 사용하기보다 깨끗한 파이썬에 의존성을 새로 설치하는 게 더 가볍고 정확하기 때문에 별로 추천하지는 않음
- 가상환경 생성
  ```
  conda create -n ENV_NAME python=3.X
  ```
- 가상환경 실행
  ```
  source activate
  ```
- 가상환경 종료
  ```
  source deactivate
  ```
- 패키지 관리
  - 패키지 관리는 pip과 requirements.txt로 함
    ```
    # 설치
    conda env create -f conda_requirements.txt

    # Lock
    conda env export > conda_requirements.txt
    ```


## pyenv-virtualenv
- pyenv의 플러그인으로, virtualenv를 이용해 가상환경을 관리해준다. 파이썬 버전을 쉽게 변경할 수 있다는 장점이 있지만 최근에는 많이 사용하지 않고있다.
  - 가상환경 설치
  - 가상환경 생성
  - 가상환경 실행
  - 가상환경 종료
  - 패키지 관리

## virtualenv
- 설치
  ```
  pip3 install virtualenv
  ```
- 가상환경 생성
  ```
  virtualenv ENV_NAME
  ```
- 가상환경 실행
  ```
  source ENV_NAME/bin/activate
  ```
- 가상환경 종료
  ```
  deactivate
  ```
- 패키지 관리
  - 패키지 관리는 pip과 requirements.txt로 한다
    ```
    # 설치
    pip3 install -r requirements.txt
    
    # Lock
    pip3 freeze > requirements.txt
    ```


## pyvenv
- 특징
  - Python 3.3과 3.4에서 사용하던 가상환경 도구였지만, 3.6 이후부터 사용하지 말 것이 권고되고 있음




## References

[1] [Data Scientist를 위한 TOP 4 파이썬 가상환경 비교](https://dining-developer.tistory.com/21)

[2] [파이썬 가상환경 비교(pipenv, venv, pyenv, conda)](https://devbull.xyz/python-create-environment/)