# 操作分頁

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
