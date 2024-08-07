**Error:**  
**500 : Internal Server Error**  
**The error was(1):**  
nbconvert failed: PDF creating failed, captured latex output:
Failed to run "xelatex notebook.tex -quiet" command:
xelatex: security risk: running with elevated privileges  
**The error was(2):**  
nbconvert failed: xelatex not found on PATH, if you have not installed xelatex you may need to do so. Find further instructions at https://nbconvert.readthedocs.io/en/latest/install.html#installing-tex.  
* * *
# 1. How to handle this error
1. install the pandoc
   `conda install pandoc`
2. install the nbconvert
   `conda install nbconvert`
3. install the [miktex](https://anaconda.org/conda-forge/miktex)  
   `(gc_ml_scratch) conda install conda-forge::miktex`

# 2. How to convert `.ipynb` to something
sol1. jupyter notebook -> 좌측 상단 'File' -> 'Save and Export Notebook As...'  

sol2.
```cmd
:: ipynb to pdf
(gc_ml_scratch) jupyter nbconvert --to pdf notebook_name.ipynb

:: ipynb to markdown
(gc_ml_scratch) jupyter nbconvert --to markdown notebook_name.ipynb
```
* Example:
  ```cmd
  (gc_ml_scratch) C:\gc_ml_scratch>jupyter nbconvert --to markdown CNN_classification_raisin(PyTorch).ipynb
  [NbConvertApp] Converting notebook CNN_classification_raisin(PyTorch).ipynb to markdown
  [NbConvertApp] Support files will be in CNN_classification_raisin(PyTorch)_files\
  [NbConvertApp] Making directory CNN_classification_raisin(PyTorch)_files
  [NbConvertApp] Writing 27817 bytes to CNN_classification_raisin(PyTorch).md

  (gc_ml_scratch) C:\gc_ml_scratch>dir "CNN_classification_raisin(PyTorch).md"
   C 드라이브의 볼륨에는 이름이 없습니다.
   볼륨 일련 번호: F8EF-1352

   C:\gc_ml_scratch 디렉터리

  2024-08-07  오전 11:28            30,160 CNN_classification_raisin(PyTorch).md
                 1개 파일              30,160 바이트
                 0개 디렉터리  199,946,915,840 바이트 남음
  ```
