# GEE_Python

This project is for using Google Earth Engine(GEE) with Python3 language.
I follow the suggestion from GEE, using **Google Colab** in the project.
Here are the introduction of each function in the project：

## 1. GEEtoXarray
This function is used to transfer GEE satellite image into Xarray's **DataArray** file format. 
The time-seires images of ROI will be stored in a 4-D DataArray. The output file could be further saved as **netCDF4** file.



## ---Chinese Version of Introduction---
>遙感探測(Remote sensing),簡稱為遙測,是透過衛星或任何飛行器搭載觀測儀器,達成遠距離觀測地球表面的目的。在森林學領域中,有一個分支便是利用遙測技術進  >行資源探勘與管理。林學領域會用到的影像來源包含飛機、無人機、衛星等,其中衛星影像因為具有定期拍攝的性質,而被廣泛用於各種監測研究。過往要進行衛星影像 >分析,有幾個大問題需要克服:
>  1. 電腦的容量,大量的衛星影像需要很大的空間儲存。
>  2. 電腦的運算速度(包含 RAM 容量),電腦要運算大量的圖資,基本上很吃運算資源,不夠好的電腦就會跑半天可能還沒辦法得到一張圖;如果 RAM 太小,往往也會導致分析無法進行。  

>如果想要分析長期累積的影像,上述兩點幾乎是一般學生無法克服的困難。基於此,為了讓更多人可以利用這些開放圖資,目前的趨勢是將影像儲存與資料分析都置於雲端>平台,個人使用者只需要透過瀏覽器下達指令即可連線遠端電腦完成運算,傳回所需結果。

Google Earth Engine(GEE)便是由 Google 開發並開放免費使用的雲端衛星資料分析平台。Google 將重新分類的衛星資料儲存於 Google Cloud 雲端服務中,並開放使用者透過 GEE 平台編寫 code,調用衛星影像進行分析。官方提供兩種程式語言供使用者操作 GEE, 1.是透過瀏覽器 IDE 編寫的 Javascript, 2.是 python 語言。 

Python 作為兩大資料科學主流語言,已有相當成熟的技術與許多社群致力開發許多科學分析 library(e.g. Scipy 生態系);近年來也有社群希望統合地球科學
分析相關重要library,使之成為一個分析平台(e.g. Pangeo)。GEE api利用特別設計的格式來儲存影像物件，並透過GEE的演算法來進行分析，同時提供將資料取出的函式,以便讓有需求的使用者可以自行完成資料的取用。  

因為並未找到相關已存在的轉換函數,本 project 選擇將其轉為 xarray 中的 ”DataArray”,此一專為多維矩陣運算所設計的格式,以便界接。

<p align="center">
<img src="https://github.com/YTHsieh/GEE_Python/blob/master/Pictures/GEE_Scipy_project.JPG" width="440" height="300">
</p>
<p align="center">
圖1. 本專案流程圖
</p>

轉檔完成的 DataArray 具有三個維度,分別為衛星影像的經度、緯度與時間軸。觀測值(如 NDVI、溫度、降水量等)依上述維度分別存於對應的欄位,若有一個以上的觀測值,則增加新的維度以儲存,在 xarray 中稱這些觀測值欄位為 Data variables,原則上Data variables的儲存沒有上限,端看需求。完成轉檔後,DataArray可以選擇另存為”.netCDF4”格式,並使用相關 function 進行分析,在此我們列出各時間點的 NDVI 觀測值與繪出選定區域的平均 NDVI 變化曲線。

<p align="center">
<img src="https://github.com/YTHsieh/GEE_Python/blob/master/Pictures/GEE_Scipy_project_result.JPG" width="440" height="300">
</p>
<p align="center">
圖2. 結果Demo
</p>
