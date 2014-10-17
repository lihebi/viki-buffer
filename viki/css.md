#css

#position

##static
正常
##relative
相对于正常。如果不设top,left,..，则无变化。
其引入两个特征：
1. 可以使用`z-index`了。如果不指定`z-index`，它会出现在所有`static`元素的上方。
2. 其子元素，若是`absolute`，其`absolute`的区域是此`relative`
##absolute
相对于一个`relative`或`absolute`的父节点。若无，则`hmtl`。
从`flow`中消失，不会影响也不会受其他元素影响。
##fixed
相对于`viewport`来说。

#!important
color: red !important;

#inline-block item 之间会有默认的space，如何除去：

1. 把parent的font-size设为0
2. 把所有元素放到一行，中间没有空格
3. 把所有元素的换行用注释去掉
4. 把</div>的>放到下一行的开始

#bootstrap
bootstrap glyphicon
<span class="glyphicon glyphicon-search” style=“color: blue"></span>
