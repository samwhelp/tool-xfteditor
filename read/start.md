---
title: 緣起
nav_order: 1
has_children: false
---

# 緣起

以前發現用「mousepad」開啟檔案，若陸續開啟檔案，則會在「mousepad」開啟新的「Tab」，

後來發現原來「[xfce4-terminal](https://man.archlinux.org/man/xfce4-terminal.1.en#Window_or_Tab_Separators)」，有一個「--tab」的參數可以下，

於是就有了這個專案，把我的想法實踐出來，

就是以下個功能，以「[xftvim](https://samwhelp.github.io/tool-xfteditor/read/project/xfteditor/xftvim.html)」為例。

1. 開啟檔案管理器，例如使用 `thunar`
2. 點選某個檔案
3. 滑鼠右鍵，選擇開啟使用「Xftvim」，
4. 就會開啟 xfce4-terminal，並且開啟新的分頁，並且使用「vim」開啟該檔案。

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
