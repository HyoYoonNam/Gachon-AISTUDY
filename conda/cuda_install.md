**2024.08.01 Windows10 22H2**  
# 1. 본인이 사용하려는 PyTorch Version에서 지원하는 CUDA Version 확인
[여기](https://pytorch.org/get-started/previous-versions/)에서 본인이 사용하려는 PyTorch Version을 `Ctrl+F`로 검색하면 



```cmd
:: 그래픽카드 버전 확인 on cmd
nvidia-smi
:: 상단에 NVIDIA-SMI, Driver Version, CUDA Version이 출력된다
```
![output](https://github.com/user-attachments/assets/bf7a1dca-87cc-4218-a164-5f89473c9c19)  
*output: 본인 컴퓨터 기준으로는 12.5version까지 호환이 가능하다.*  
legacy version 등에 대한 compatability를 확인하려면 [여기](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html#cuda-major-component-versions)에서 table2. table3.를 확인  

[CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive)
