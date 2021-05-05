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

#--------------------------------------------------------------------------------------#

## 觸媒壽命預測模型
1.將觸媒數據匯入，以2016/6/1 00:00開始為第一筆數據，接著開始擷取重要因子變數。

2.將入料量的缺失值或NA值以0取代之。再獨立新增一個空欄位作為存放累加入料量使用。

3.把時間獨立出來以便後續抓取特定日期；將目標值(Y，出口溫度-鹽浴溫度0757A(溫差))獨立拉出。

4.新增一個空的資料框架格式，裡面存放：時間序列(ts)、觸媒使用時間(timeserver)，目標值(Y)、鹽浴溫度0757A、入料量(累加)。

5.建立非線性迴歸模型，並進行預測。

6.預測值本身不代表意義，因此使用機率面積來換算。將預測值平滑至最小值為0。

7.將每一個預測值除上總值，並每一個預測值點都進行累加，最後累加值會等於1。

8.每一個時間下的累加值，即為觸媒耗用程度，再用1減去該耗用程度，所得觸媒剩餘壽命。
