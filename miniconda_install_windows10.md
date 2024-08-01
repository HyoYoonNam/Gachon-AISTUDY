# 1. Miniconda 설치 및 환경변수 설정(Windows10)
[Download Miniconda](https://docs.anaconda.com/miniconda/)  
1. checkbox나 path 설정 등을 모두 default로 유지하고 설치를 완료한다.
2. `window` 키를 눌러 '시스템 환경 변수 편집'를 검색하여 클릭하고, '환경 변수'를 클릭한다.
3. '시스템 변수'에서 '새로 만들기'를 누르고 다음과 같이 환경변수를 추가하고 저장한다('유저네임'부분은 본인 시스템에 맞게 변경).  
   변수 이름: PATH
   변수 값: C:\Users\유저네임\miniconda3;C:\Users\유저네임\miniconda3\Scripts;C:\Users\유저네임\miniconda3\Library\bin
4. cmd에서 `conda --version`을 입력했을 때 version info가 리턴된다면 완료.

# 2. conda 기본 설정
```cmd
:: conda virtual environment(가상 환경) 생성
:: 'gc_ml_scratch' 부분은 본인이 원하는 가상 환경의 이름으로 변경 가능
conda create -n gc_ml_scratch python=3.6 -y
conda init
:: 이후에 cmd 재실행
```

```cmd
:: virtual environment로 진입
:: conda deactivate로 진입한 virtual env를 비활성화 가능
conda activate gc_ml_scratch

:: workspace 생성 후 이동
:: 'gc_ml_scratch' 부분은 본인이 원하는 workspace 이름으로 변경 가능
mkdir C:\gc_ml_scratch && cd C:\gc_ml_scratch
```

```cmd
:: 기본 library 설치
:: numpy는 pandas설치 시 종속적으로 설치됨
conda install juptyer pandas matplotlib seaborn -y
```

# 3. Jupyter Notebook 실행
```cmd
:: Jupyter Notebook 실행
:: working directory를 workspace로 설정하고 수행할 것
jupyter notebook
```

나중에 참고할 것: [CUDA 설치](https://80000coding.oopy.io/d8131e92-bde9-4526-a604-217ef31d5a86)
