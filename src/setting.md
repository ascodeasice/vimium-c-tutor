# 設定

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
