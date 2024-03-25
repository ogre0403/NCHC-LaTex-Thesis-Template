# NCHU LaTex Thesis Template (中興大學 LaTeX 論文模板)

中興大學校方提供的LaTex論文模板已經無法下載，從[中興大學企管系網頁](http://ba.nchu.edu.tw/front/Downloads/archive1/archive.php?ID=bmNodV9pYiZhcmNoaXZlMQ==&no=10)取得此模板，並進行修改。

## 特性

### 支援xeCJK

原先模版裡的中文是big5編碼，需要先由cwTeX進行前處理後，才可由LaTeX編譯。改用xeCJK套件，支援UTF-8編碼，由xelatex進行編譯。

### 支援bibtex

原先模版裡的參考文獻是使用 `enumerate`環境列舉參考文獻，改成使用bibtex進行編譯。

### 重構檔案目錄結構

將每個章節的tex檔分開，放在`manuscripts`資料夾下；所有圖片放在`figures`資料夾，方便管理。

## 使用方法

### 編譯步驟

xelatex -> bibtex -> xelatex * 2


### 使用 devcontainer

1. 透過VSCode的devcontainer 提供TeXLive的環境，可以直接使用LaTeX編譯。已經安裝所有編譯樣版必要的套件，及安裝好中文字型。
2. 若需要其他TeXLive套件，可以在`.devcontainer/Dockerfile`中加入安裝指令。
3. 已安裝VSCode的LaTeX Workshop套件，可以直接使用快捷鍵進行編譯。


### 修改中文字型

1. 若要修改中文字型，可以在 `thesis.tex` 中修改 `\setCJKmainfont` 設定。
2. 預設採用[教育部標準楷書](https://language.moe.gov.tw/001/Upload/Files/site_content/M0001/edukai.pdf)。若是用devcontainer安裝環境，字型已安裝完成，可以直接使用。
3. 在Linux，使用`fc-list`查詢可用的字型；若在Windows下，直接改成要使用的字型名稱。


