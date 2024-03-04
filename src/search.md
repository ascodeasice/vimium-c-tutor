# 自訂搜尋引擎

## 搜尋

- 可以更改自己的預設搜尋引擎
`https://www.google.com/search?q=$s`

- 可以自訂一些在 Omnibar 中的搜尋引擎，有簡寫、網址、顯示名稱，格式為：


```
簡寫|可不加的簡寫二|可不加的簡寫三: 網址（可以放$s） 顯示名稱
```

當在 Omnibar 輸入

```
簡寫 搜尋字
```

時，如果有對應的搜尋引擎會顯示"顯示名稱"＋"網址"，並用搜尋字替換 $s

例如：

新增
```
gh: https://github.com/search?q=$s&type=repositories All github repo
```

輸入 gh vimium 會顯示

![All github repo: vimium, github.com/search?q=vimium&type-repositories](./assets/custom-search.png)

## 簡寫

也可以只輸入簡寫，並每次都到固定的網址，當作快速開啟某個網站使用（這樣做會比搜尋書籤更準確）。

例如：

```
y|yt: https://www.youtube.com Youtube 首頁
```

在 Omnibar 輸入 y 或 yt 就一定會到 youtube 首頁， 並忽略後段的搜尋字（因為定義中沒有寫到$s）

## 範例

以下是一些我常用的自訂搜尋引擎：

```
gc|calendar: https://calendar.google.com/calendar/u/0/r Google 日曆

y|yt: https://www.youtube.com Youtube 首頁
ys|yts: https://www.youtube.com/results?search_query=$s Youtube 搜尋

gm: https://www.google.com/maps?q=%s \
  blank=https://www.google.com/maps Google 地圖

vc: chrome-extension://hfjbmagddngcpeloejdejnfgbamkjaeg/pages/options.html Vimium C 設定

mgh: https://github.com/?q=$s My Github repo
gh: https://github.com/search?q=$s&type=repositories All github repo

py|python:  https://docs.python.org/3/search.html?q=$s Python文件
pt|pytorch|Pytorch|PyTorch: https://pytorch.org/docs/stable/search.html?q=$s&check_keywords=yes&area=default Pytorch 文件

lh|local|localhost: http://localhost:$s Localhost

c|cl|cloud: https://drive.google.com/drive/u/0/my-drive Google雲端硬碟

ext: chrome://extensions Google 插件
sc|sho|short: chrome://extensions/shortcuts Google 插件快捷鍵

gk|ke|keep: https://keep.google.com/u/0/#home Google Keep 筆記
note

me|meet: https://meet.google.com/ Google Meet

int: https://fast.com/zh/tw/ 網路速度
```
