## Disclaimer

- Political problems, use vimium, surfing keys, and alternatives instead
- firefox: vimium-ff, safari vimari

## Note

- Prefix numbers before action means doing action for n times

## Move

- vertical
    - k
    - j
    - gg
    - G
    - d
    - u
    - U*
    - D*
- horizontal
    - h
    - l
- Mark
    - ma
    - mA (global)
    - `a
    - `A (global)

## Tabs

- history && upper domain
    - H
    - L
    - gu
    - gU
- Switch Tabs
    - J
    - K
    - g^,gh*
    - g$,gl*
- Manipulate
    - yt
    - delete/restore tab*
        - x
        - XX*
        - XJ*
        - XH*
        - XL*
    - W
    - w*
    - t
    - Zoom*
        - zj*
        - zk*
        - Z*

- Shift Tabs
    - <*
    - >*
- Load
    - r

## Interaction

- Click
    - f
    - F
    - <a-f>*
    - C*
    - [*
    - ]*
    - a*
    - A*
- Focus && Hover
    - s*
    - S*
    - esc
        - Escape before do any action
        - if stuck on top bar and can't escape, do a tab then escape
    - gf: focus on next frame
    - gF: focus on main frame
    - gi + tab
- Copy
    - yy
    - yh* (currentTitle)
    - yp* (copy the screenshot)
    - ym*
    - yf

## Omnibar

- Basic
    - o
    - O
    - b (extra recommend: [faster bookmark](https://chromewebstore.google.com/detail/faster-bookmark-add-bookm/fibadljlplamppipiebabkdehecpabce)
    - B
    - ge
    - gE
    - T
    - p (search what's in your clipboard)
    - P
- Advanced
    - flags: `:h` for history
- Custom
    - search engine(yts, py...)
    - shortcut (int, yt, vc...)

## Visual Mode

- focus on text
    - yv, c*
    - search
        - / (can use regex)
        - n
        - N
- visual mode
    - v\[motion\]
    - V\[motion\]
    - vw, vW, v$, v}, vj...
    - o: switch cursor direction
- caret mode
    - c in visual mode + \[motion\]
        - cw, cW, c$, c}, cj...
- y to copy
- p/P to search

## Disable keys

- ex: youtube, monkeytype
- i(input mode)
- disable in gui setting

## Settings

- disable certain keys in certain websites
- custom keymap
    - different clickable in different website (env, virtual key,runKey)
    - map and unmap
    - check the document for all commands
    - parameter after command
- default browser
- custom search engine, shortcut or search in website
- if not using `#extensions-on-chrome-urls`, update the new tab url to `pages/blank.html`
- Add some text to previous/next pattern
- Custom CSS
    - download mine on [github](https://github.com/ascodeasice/vimium-c-one-dark-pro)
    - create your own with [template](https://github.com/Darukutsu/vimiumc-themes)
- Blacklist: youtube, instagram, your company name...
- Import and Export settings

## Pitfalls

- Some google official websites don't allow running extension by default, so either enable them in experimental flag, or use native shortcut
- When extension isn't working, check if the browser is focusing on top menu or not focused in browser.
- when vimium-c is not focusing on the stuff you want, try hover on it, or use `gf`
- when trying to open a pdf file and use vimium-c, download [pdf viewer ](https://chromewebstore.google.com/detail/pdf-viewer-for-vimium-c/nacjakoppgmdcpemlfnfegmlhipddanj) extension
- to change language, change display language of chrome
- waiting for extension update, then there would be traditional chinese

## Vimium Tutor

0.
    - Install
    - learn to escape ,when can't you use vimium-c (and how to use it in google official pages in advanced section)
    - go to setting, avoid focus when page is loaded
    - you can skip the advanced section in the below tutorial, and check them later, or just go through them if you're interested

1. Move
    - Move around with hjkl
    - up down half page with d, u
    - advanced: full page with D, U
        ```
            map D scrollFullPageDown
            map U scrollFullPageUp
        ```
    - advanced: move with mark (a and A can be replaced with other characters)
        - ma, mA  set local mark "a" (global mark "A")
        - `a, `A  jump to local mark "a" (global mark "A")

2. Interact with Tab
    - Click with f, F (uppercase means another page), <a-f>
    - Advanced Click: C
    ```
        map C LinkHints.activate dblclick
    ```
    - Next/Previous Page with \[\[, \]\]
        - You can remap them into \[ and \]
        - Advanced: customize the word for prev/next page detection
    - Focus and hover
        - esc, gf, gF, gi+tab
        - advanced: map s to
        ```
           map s LinkHints.activateHover
           map S LinkHints.unhoverLast
        ```
    - Copy
        - yy, yf
        - advanced: customize(TODO)
        - advanced: customize copy with mapping
            ```
                map yh copyCurrentTitle
                map yp captureTab copy

                # copy tab in markdown format
                map ym copyWindowInfo format="[${title}](${url})" type="tab"
            ```
    - Move between tabs
        - Switch Tabs with J, K, g$, g^
        - advanced: remap g$ and g^ to gl/gh
            ```
                map gh firstTab
                map gl lastTab
            ```
        - History last/next page: H, L
        - go up in url hierarchy with gu, gU
            NOTE: do gu/gU then H, L to see the effect
3. Manipulate Tab
    - yt for duplicate current tab
    - x and X for delete and restore tab
    - W for move tab to another window
    - t for opening a new tab
    - advanced: map XX, XJ, XH, XL
    ```
        unmap X
        map XH closeTabsOnLeft
        map XL closeTabsOnRight
        map XX closeOtherTabs
        map XJ restoreTab
    ```
    - << and >> to shift tab
        - advanced: map to < and >
        ```
            unmap <<
            unmap >>
            map < moveTabLeft
            map > moveTabRight
        ```
    - r for reload tab
    - advanced: w to pin tab
    ```
        map w togglePinTab
    ```
    - advaned: zoom with Z, zj, zk
        ```
            map zj zoomIn
            map zk zoomOut
            map Z zoomReset
        ```
    - advanced: download link/image with a, A
        ```
            map a LinkHints.activateDownloadLink
            map A LinkHints.activateDownloadImage
        ```
4. Omnibar
    - o and O for search in default or customized search engine
    - b and B for search in bookmark
    - (extra recommend: [faster bookmark](https://chromewebstore.google.com/detail/faster-bookmark-add-bookm/fibadljlplamppipiebabkdehecpabce)
    - update current url with ge or gE
    - search active tabs with T
    - advanced: add flags: `:h` for history
    - Custom search engine
        - syntax: identifier url displayName
        - search: identifier extraString
        - $s is the word after the search
        - search engine(yts, py...)
            ```
                ys|yts: https://www.youtube.com/results?search_query=$s Youtube 搜尋
                my-gh|mygh|mgh: https://github.com/?q=$s My Github repo
                gh: https://github.com/search?q=$s&type=repositories All github repo
                lh|local|localhost: http://localhost:$s Localhost
            ```

        - shortcut (int, yt, vc...)
            ```
                y|yt: https://www.youtube.com Youtube 首頁
                ext: chrome://extensions Google 插件
                sc|sho|short: chrome://extensions/shortcuts Google 插件快捷鍵
                c|cl|cloud: https://drive.google.com/drive/u/0/my-drive Google雲端硬碟
            ```
5. Select text
    - focus on text
        - yv, or remap to c
            ```
                map c LinkHints.activateSelect
            ```
        - search for using visual mode
            - / (can use regex)
            - n
            - N
    - visual mode
        - v\[motion\] for character selection
        - V\[motion\] for whole line selection
        - vw, vW, v$, v}, vj...
        - o: switch cursor direction
    - caret mode
        - c in visual mode + \[motion\]
            - cw, cW, c$, c}, cj...
    - y to copy
    - search what is in clipboard with p or P

6. Disable keys

    - ex: youtube, monkeytype
    - i(input mode)
    - disable in gui setting

7. Settings

    - disable certain keys in certain websites
    - custom keymap
        - different clickable in different website (env, virtual key,runKey)
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
        - map and unmap
        ```
            unmap <<
            unmap >>
            map < moveTabLeft
            map > moveTabRight
        ```
        - check the [document](https://github.com/gdh1995/vimium-c/wiki/List-of-all-commands) for all commands
        - parameter after command
    - default browser
    - custom search engine, shortcut or search in website
    - if not using `#extensions-on-chrome-urls`, update the new tab url to `pages/blank.html`
    - Add some text to previous/next pattern
    - Custom CSS
        - download mine on [github](https://github.com/ascodeasice/vimium-c-one-dark-pro)
        - create your own with [template](https://github.com/Darukutsu/vimiumc-themes)
    - hide search result: youtube, instagram, your company name...
    - Import and Export settings

7. Pitfalls

    - Some google official websites don't allow running extension by default, so either enable them in experimental flag, or use native shortcut
    - When extension isn't working, check if the browser is focusing on top menu or not focused in browser.
    - when vimium-c is not focusing on the stuff you want, try hover on it, or use `gf`
    - when trying to open a pdf file and use vimium-c, download [pdf viewer](https://chromewebstore.google.com/detail/pdf-viewer-for-vimium-c/nacjakoppgmdcpemlfnfegmlhipddanj) extension
    - to change language, change display language of chrome
    - waiting for extension update, then there would be traditional chinese

