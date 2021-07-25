---
title: 緣起
nav_order: 1
has_children: false
---

# 緣起

以前發現用「mousepad」開啟檔案，若陸續開啟檔案，則會在同一個「mousepad」開啟新的「Tab」，

後來發現原來「[xfce4-terminal](https://man.archlinux.org/man/xfce4-terminal.1.en#Window_or_Tab_Separators)」，有一個「--tab」的參數可以下，

於是就有了這個專案，把我的想法實踐出來，

就是以下個功能，以「[xftvim](https://samwhelp.github.io/tool-xfteditor/read/project/xfteditor/xftvim.html)」為例。

1. 開啟檔案管理器，例如使用 `thunar`
2. 點選某個檔案
3. 滑鼠右鍵，選擇開啟使用「Xftvim」，
4. 就會開啟「xfce4-terminal」，並且開啟新的分頁，並且使用「vim」開啟該檔案。

## 實做簡述

### Shell Script

實做這個功能的基本指令如下

``` sh
xfce4-terminal --tab --command="vi $HOME/.bashrc"
```

所以把這個功能，包裝成一個「Shell Script(腳本)」，

以上面為例，就是「[xftvim](https://github.com/samwhelp/tool-xfteditor/blob/gh-pages/_demo/project/xfteditor/prototype/xftvim/xftvim#L83)」。

將這個檔案，[安裝](https://github.com/samwhelp/tool-xfteditor/blob/gh-pages/_demo/project/xfteditor/prototype/xftvim/Makefile#L18)到「/usr/local/bin/xftvim」這個路徑。

### Desktop Entry

接下來在產生一個「[xftvim.desktop](https://github.com/samwhelp/tool-xfteditor/blob/gh-pages/_demo/project/xfteditor/prototype/xftvim/xftvim.desktop)」，

將這個檔案，[安裝](https://github.com/samwhelp/tool-xfteditor/blob/gh-pages/_demo/project/xfteditor/prototype/xftvim/Makefile#L19)到「/usr/share/applications/xftvim.desktop」這個路徑。

這樣在「檔案管理器」就可以使用滑鼠右鍵，開啟選單，選擇使用「Xftvim」開啟某個檔案。


## 後續

所以根據這個模式，針對不同的「文字編輯器」，產生相對應的「[輔助工具](https://samwhelp.github.io/tool-xfteditor/read/project/xfteditor/)」。

另外有一個工具「[xfted](https://samwhelp.github.io/tool-xfteditor/read/project/xfteditor/xfted.html)」，是可以設定環境變數「EDITOR」，就會依據該設定，使用不同的文字編輯器

另外有一個工具「[xftt](https://samwhelp.github.io/tool-xfteditor/read/project/xfteditor/xftt.html)」，則是搭配「檔案管理器」用來在同一個「xfce4-terminal」開啟新「Tab」，
並且切換到相對應的資料夾。


## 平舖視窗

這個模式，可以搭配「平舖視窗管理器」，可以分割上下兩部份，或是分割左右兩部份，

舉例:「thunar」放上方，「xfce4-terminal」放下方。

我最近在使用的「平舖視窗管理器」是「[herbstluftwm](https://samwhelp.github.io/note-about-herbstluftwm/)」。

或是在「xfce4」這個環境，除了可以用「滑鼠拖曳」來「平舖視窗」，

也可以使用「鍵盤按鍵組合」來「平舖視窗」

可以參考我的設定

* Manjaro / [xfce4-keyboard-shortcuts.xml](https://github.com/samwhelp/note-about-manjaro/blob/gh-pages/_demo/adjustment/full/xfce/config/xfce4/xfconf/xfce-perchannel-xml/xfce4-keyboard-shortcuts.xml#L189)
* Ubuntu 20.04 / [xfce4-keyboard-shortcuts.xml](https://github.com/samwhelp/play-ubuntu-20.04-plan/blob/master/prototype/xfce/config/xfce4/xfconf/xfce-perchannel-xml/xfce4-keyboard-shortcuts.xml#L183)

``` xml
<property name="&lt;Shift&gt;&lt;Alt&gt;k" type="string" value="tile_up_left_key"/>
<property name="&lt;Shift&gt;&lt;Alt&gt;j" type="string" value="tile_up_right_key"/>
<property name="&lt;Shift&gt;&lt;Alt&gt;h" type="string" value="tile_down_left_key"/>
<property name="&lt;Shift&gt;&lt;Alt&gt;l" type="string" value="tile_down_right_key"/>
<property name="&lt;Primary&gt;&lt;Alt&gt;k" type="string" value="tile_up_key"/>
<property name="&lt;Primary&gt;&lt;Alt&gt;j" type="string" value="tile_down_key"/>
<property name="&lt;Primary&gt;&lt;Alt&gt;h" type="string" value="tile_left_key"/>
<property name="&lt;Primary&gt;&lt;Alt&gt;l" type="string" value="tile_right_key"/>
```

按鍵組合表格說明，請參考

* Manjaro 探索筆記 / [xfce4 keybind](https://github.com/samwhelp/note-about-manjaro/blob/gh-pages/_demo/adjustment/full/xfce/spec-keybind.md#window-tiling-move--side)
* Ubuntu 20.4 / [xfce4 keybind](https://github.com/samwhelp/play-ubuntu-20.04-plan/blob/master/prototype/xfce/spec-keybind.md#window-tiling-move--side)
