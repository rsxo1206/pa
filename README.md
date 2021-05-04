# pa
## Installation
先確保電腦有安裝了Anaconda跟git

1.先在Anaconda建立虛擬環境，給他一個獨立全新環境作業空間
在命令提示字元中(cmd)輸入
```
conda create -n pa_case_env python=3.7
```
2.然後機活該虛擬環境
```
conda activate pa_case_env
```
3.開始安裝所需要的套件，安裝好後記錄下來成一個文字檔，之後可以直接用匯入的
在pa_case_env虛擬環境下切換目錄到pa資料夾底下
```
cd pa
```
4.安裝必要的套件
```
pip install -r requirements.txt
```
過程中如果沒有報錯至此整個安裝完成。

5.如果需要看裝了什麼套件跟套件版本就打
```
pip list
```
6.在jupyter中自由切換虛擬環境，以方便專案可以在對的工作區作業
重新打開命令提示字元(cmd)輸入
```
conda install nb_conda
```
7.之後就能在jupyter下自由切換虛擬環境
ex：example.ipynb-->Kernal-->Change Kernal-->切換成自己想要的虛擬環境
