---
layout: post
title: "[转]Linux Mint 12 - iBus没有输入法图标的问题"
date: 2012-03-05 14:15
comments: true
categories: 
---
裝好Linux Mint跟iBus後發現切換輸入法時iBus的系統匣顯示的是禁止符號的圖示，我使用的解決方法是在 `/usr/share/ibus/ui/gtk/panel.py`這個檔案中加入下面＋號後兩行的程式碼(因為是Python語法所以要注意程式碼前的空格數)：
```python
    def state_changed(self):
        if not self.__focus_ic:
            return

        enabled = self.__focus_ic.is_enabled()
        self.__language_bar.set_enabled(enabled)

        if enabled == False:
            self.reset()
            self.__set_im_icon(ICON_KEYBOARD)
            self.__set_im_name(None)
        else:
            engine = self.__focus_ic.get_engine()
            if engine:
+               pixbuf = gdk.pixbuf_new_from_file(engine.icon)
+               gtk.icon_theme_add_builtin_icon(engine.icon, 0, pixbuf)
                self.__set_im_icon(engine.icon)
                self.__set_im_name(engine.longname)
            else:
                self.__set_im_icon(ICON_KEYBOARD)
                self.__set_im_name(None)
```
這樣系統匣的輸入法圖示就可以正常顯示了

[原文](http://dust-way.blogspot.com/2011/12/linux-mint-12-ibus.html "Linux Mint 12 安裝筆記 - iBus 系統匣輸入法圖示顯示問題排除")

另，如果ibus的提示框不跟随，可能是`ibus-gtk3`没有安装。
