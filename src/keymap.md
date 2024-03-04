# 自訂快捷鍵

Vimium-C 有許多可以自訂的快捷鍵，也可以把原本的快捷鍵刪除，改成用其他的鍵代替

## 在不同網頁有不同指令

我目前會需要這個的功能是在不同網頁新增/減少可以點擊的物件（因為有些可以點的東西不一定是 button 或 anchor tag）

```
        env rm host="https://roadmap.sh/"
        env gh host="https://github.com/"
        env po host="https://getpocket.com/"
        env hm host="https://hackmd.io/"

        map f runKey expect={"rm":"<v-rm_f>","gh":"<v-gh_f>","po":"<v-po_f>","hm":"<v-hm_f>"} keys="<v-f>"
        map <v-rm_f> LinkHints.activate clickable=".clickable-group"
        map <v-gh_f> LinkHints.activate clickable=".octotree-toggle"
        map <v-po_f> LinkHints.activate clickable=".css-8w5dx7"
        map <v-hm_f> LinkHints.activate clickable=".CodeMirror-line"
        map <v-f> LinkHints.activate
```

加入上方的 mapping 讓我可以在 roadmap.sh 點到原本不能點到的 \<rect\> 物件，開啟連結，遇到想加上東西的時候可以這樣寫。

## 映射與取消映射

可以更改快捷鍵的映射，可以新增自己的按鍵，也可以把原本的映射刪除。

我自己用的映射：

```

#下載連結與圖片
map a LinkHints.activateDownloadLink
map A LinkHints.activateDownloadImage

# hover 與取消 hover(用來聚焦)
map s LinkHints.activateHover
map S LinkHints.unhoverLast

# 比較好按的 g$ 和 g^
map gh firstTab
map gl lastTab

# 比較好按
unmap <<
unmap >>
map < moveTabLeft
map > moveTabRight

# 比較好按
unmap [[
unmap ]]
map [ goPrevious
map ] goNext

# 用大寫翻整頁
map D scrollFullPageDown
map U scrollFullPageUp

# 把目前網站的截圖複製到剪貼簿
map yp captureTab copy

# 用 c 聚焦 visual mode 的文字，C 用來連點
map c LinkHints.activateSelect
map C LinkHints.activate dblclick

# 複製目前分頁的 title
map yh copyCurrentTitle

# 用 markdown 格式複製目前分頁
map ym copyWindowInfo format="[${title}](${url})" type="tab"

# 放大縮小與恢復
map zj zoomIn
map zk zoomOut
map Z zoomReset

# 關閉目前左側/右側所有分頁，或目前分頁外所有分頁
unmap X
map XH closeTabsOnLeft
map XL closeTabsOnRight
map XX closeOtherTabs
map XJ restoreTab

# 釘選目前分頁
map w togglePinTab
```

- 可以在 [GitHub 文件中](https://github.com/gdh1995/vimium-c/wiki/List-of-all-commands) 找到所有 command
