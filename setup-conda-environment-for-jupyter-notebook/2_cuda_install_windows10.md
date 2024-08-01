**2024.08.01 Windows10 22H2**  
# 1. PyTorch - Python - CUDA의 Compatibility Matrix 확인
[여기](https://github.com/pytorch/pytorch/blob/main/RELEASE.md#release-compatibility-matrix)에서 PyTorch - Python - CUDA의 Compatibility를 확인할 수 있다.  
위 사이트를 잠시 띄워놓고 다음으로 넘어간다.


# 2. 본인의 Graphic Card(GPU)와 CUDA의 Compatibility 확인
```cmd
:: 그래픽카드 드라이버 버전 및 CUDA 버전 확인 on cmd
nvidia-smi
:: 상단에 NVIDIA-SMI, Driver Version, CUDA Version이 출력된다
```
![output](https://github.com/user-attachments/assets/bf7a1dca-87cc-4218-a164-5f89473c9c19)  
*output: 여기서 `Driver Version`을 기억해두자.*  

[여기](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html#id4)에서 본인의 Driver Version으로 호환 가능한 CUDA 버전을 확인한다.  
![b](https://github.com/user-attachments/assets/11a420b7-3835-49f2-833f-085f741f972f)  
*2024.08.01 기준 가장 최신 버전의 CUDA인 `CUDA 12.x` 버전은 `Driver Version >= 528.33`이라면 가능하다.*  
*나는 `556.12`이므로 Table의 모든 CUDA와 호환된다.*


# 3. Download and Install CUDA Toolkit
[1.에서 띄워놓은 사이트](https://github.com/pytorch/pytorch/blob/main/RELEASE.md#release-compatibility-matrix)에서 본인이 사용하려는 PyTorch Version에 권장되는 Stable CUDA Version을 확인한다.  
나는 `PyTorch 2.1`을 사용할 것이고, 이에 대한 Stable CUDA는 	`CUDA 11.8, CUDNN 8.7.0.84`이다(CUDNN은 CUDA설치시에 같이 설치되니 신경쓰지 않아도 됨).  

[여기](https://developer.nvidia.com/cuda-toolkit-archive)에서 Stable CUDA Version과 동일한 Version의 CUDA Toolkit을 다운받고, 설치한다. 내 경우에는 `CUDA Toolkit 11.8.0`이다.  
> CUDA Toolkit을 설치까지 완료한 후에 다음 챕터로 넘어가야 한다.


# 4. Download pytorch and cuda on Conda Environment
[참고](https://github.com/rudevico/Gachon-AISTUDY/blob/main/conda/miniconda_install_windows10.md) 지금부터 기존에서 만들어뒀던 conda env에서 진행한다.  
```cmd
:: pytorch, torchvision, torchaudio, pytorch-cuda 설치
(gc_ml_scratch) conda install pytorch==2.1.0 torchvision==0.16.0 torchaudio==2.1.0 cudatoolkit=11.8 -c pytorch -c nvidia
```
*`pytorch` version과 호환되는 `torchvision`, `torchaudio`은 [여기](https://pytorch.org/get-started/previous-versions/#v210)에서 확인할 수 있다.*
*pytorch만 사용하는 경우에는 `cudatoolkit`대신 `pytorch-cuda`로 설치하는 것이 더 좋은 성능을 낼 수 있다.*
*본인은 추후에 tensorflow와 pytorch를 모두 사용할 것 같아서 `cudatoolkit`으로 설치했다.*

# 5. Install 확인
```cmd
:: conda env에서 python 실행
(gc_ml_scratch) python
```

```python
>>> import torch # pytorch를 import
>>> torch.cuda.is_available() # cuda(gpu)가 사용 가능한지 확인
True
```

이제 pytorch에서 gpu(cuda)를 사용할 수 있다. 물론 cpu도 사용할 수 있다.

# 6. Jupyter Notebook에서 cuda 사용하기
해당 챕터를 진행하기 전에 ipython의 kernel을 `gc_ml_scratch`로 설정해야 한다.  자세한 방법은 [여기](https://github.com/rudevico/Gachon-AISTUDY/blob/main/setup-conda-environment-for-jupyter-notebook/miniconda_install_windows10.md#3-%EC%A4%91%EC%9A%94ipython-kernel%EC%9D%84-conda-environment%EB%A1%9C-%EC%A7%80%EC%A0%95%ED%95%98%EA%B8%B0)를 참고.
```cmd
:: python에서 exit()하고, 다음 명령을 실행
(gc_ml_scratch) jupyter notebook

:: web에서 jupyter notebook 실행됨
```
(실행된 web 화면 기준) 우측 상단에 `New` -> `Notebook` 클릭 -> `Select Kernel` 창이 뜨는데, 이때 `gc_ml_scratch`로 설정하고 시작한다.  
> kernel을 `gc_ml_scratch`로 설정하고 실행된 jupyter notebook에서는 conda envrionment인 `gc_ml_scratch`에 설치된 모든 패키지들(pandas, matplotlib, seaborn, torch, cuda, ...)을 별도의 install없이 바로 `import`할 수 있다.

![c](https://github.com/user-attachments/assets/fffcd1c1-1882-44fa-bb47-62d53c8f8210)  
*앞선 과정에서 conda environment인 `gc_ml_scratch`에 `torch` library를 설치해놨기 때문에 `gc_ml_scratch`를 kernel로 사용하는 notebook에서는 곧바로 `import`할 수 있다.*  
