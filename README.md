# Development-Environment

---

### 목표 : VSocde(window10)에서 GPU를 활용한 ML/DL 개발환경 구축

  * 준비물 : CUDA , cuDNN , anaconda , VScode

## CUDA 설치

#### CUDA를 사용하는 이유

* GPU(Graphics Processing Unit)이라고 알려진 그래픽카드를 프로그래밍 시에 사용 하고 싶기 때문
* GPU는 CPU와 달리 엄청나게 많은 연산을 동시에 진행함
* CPU는 보통 single-core 연산을 하거나 OpenMP를 통하여 Multi-cores 연산을 하지만 , GPU는 Many-cores 연산을 진행함

1. 본인 GPU 확인
	
	시작 - 찾기 - 장치 관리자

2. GPU Compute Capability 확인

	RTX-2060 >> Compute Capability : 7.5

3. CUDA SDK 확인

	CUDA를 설치 하기 전에 CUDA에는 여러가지 Version이 있는데 이 버전은 본인의 GPU와 연관이 있으므로 GPU의 Compute Capability를 기억하고 CUDA version을 선택해야 함

	RTX 2060의 경우 Compute Capability가 7.5 이니 CUDA 10.0 version을 다운 받았음

4. CUDA 설치

	사이트에 들어가 자신의 OS에 맞게 다운 받고 설치를 진행하면 된다. (환경 변수 등록은 자동으로 됨)


5. cuDNN 설치

* 멤버쉽 가입 : nvidia에 가입을 해야만 설치가 가능하다.
* CUDA 버전에 맞는 cuDNN을 선택해서 다운 받는다.
* 본인의 OS에 맞는 버전으로 설치해준다
* 다운로드가 완료 되면 아래와 같이 다운로드 된 경로에 ‘cuda’ 라는 파일이 생기고 하위 디렉토리에 파일이 생성되어 있음

	경로이동 : 위 cuda 파일의 bin , include , lib 안에 있는 것들을 아까 설치 한 CUDA의 경로에 알맞게 각각 넣어 줌
 
 ----
 
 ## 가상환경
 
 #### 가상환경이란?
 * 가상환경(Virtual Environments)이란 자신이 원하는 Python 환경을 구축하기 위해 필요한 모듈만 담아 놓는 바구니라고 생각하면 됩니다.
* 즉 아래의 사진 처럼 Python Virtual Envs 처럼 각 가상환경(virtualenv1 , virtualenv2 )은 독립적으로 관리됩니다.
* 가상환경을 이용하지 않고 모듈을 마구잡이로 설치하다 보면 , 각 모듈은 다른 모듈에 대한 의존성(dependency)이 다르기 때문에 오류가 발생할 수 있습니다.
* 따라서 각 프로젝트 별로 별개의 가상환경을 만들어 놓고 사용하는 것이 효율적인 프로젝트 관리 방법입니다.

## Anaconda 

#### 아나콘다(Anaconda)란?
 * 쉽게 말해 , 라이브러리들을 쉽게 설치하고 관리할 수 있게 해주는 도구
 * Python은 기본적으로 패키지 관리 시스템인 pip만을 포함하고 있다
 * 때문에 필요한 툴 , 패키지가 있다면 pip를 통해 수동으로 추가해야 한다.
