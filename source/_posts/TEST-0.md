---
title: TEST
date: 2022-07-11
description: 用來測試 hexo 的指令
tags: [TEST]
categories:
- [測試]
---


這裡是用來測試 Hexo 的程式碼出來的效果用的 (以下內容均參考[{% label Butterfly orange%}](https://butterfly.js.org/))。<br><br>

# Butterfly

{% hideBlock display,bg,color %}
嘿嘿
{% endhideBlock %}

{% hideToggle display,bg,color %}
content
{% endhideToggle %}

{% note [class] [no-icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}

{% note blue 'fas fa-bullhorn' simple %}
content
{% endnote %}

{% mermaid %}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
{% endmermaid %}

{% note info simple %}
info 提示塊標籤
{% endnote %}

{% note success modern %}
success 提示塊標籤
{% endnote %}

{% tabs test1 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->

<!-- tab @fab fa-apple-pay -->
**只有圖標 沒有Tab名字**
<!-- endtab -->
{% endtabs %}


{% flink %}
- class_name: Link
  class_desc: Hexo
  link_list:

    - name: Hexo
      link: https://hexo.io/zh-tw/
      avatar: https://d33wubrfki0l68.cloudfront.net/6657ba50e702d84afb32fe846bed54fba1a77add/827ae/logo.svg
      descr: 快速、簡單且強大的網誌框架
{% endflink %}
<hr>
<label for="fname">TEST: </label> <input type="text" id="fname" name="fname">
<hr>

測試 hexo 張貼 youtube 影片連結(需有影片ID -> 分享 -> 網址後面一串英文):
{% youtube dQw4w9WgXcQ %}


# Hexo docs.

## Block

這裡是從 [Hexo](https://hexo.io/docs/tag-pluginsn) 擷取 ，更多資源可以去該網看看。

{% blockquote %}
content
{% endblockquote %}

{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}

{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}

{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}

{% codeblock Array.map %}
array.map(callback[, thisArg])
{% endcodeblock %}

## Others

(暫無內容)

<br><br>

