宗旨
========

Kickstrap（内置bootstrap）是超屌的快速构建HTML5应用的前端框架集大成者，他基于bootstrap加入了主题功能，HTML5Boilerplate，IE6兼容插件，和各种酷炫插件，特别是图标采用了font-awesome。

然而由于项目元素较多，文档不够详尽，目前使用起来有些不便之处，这里根据我的实际运营的项目，对它进行一些修订，这里专门刊出与主项目不同之处，所以在使用时，先下载Kickstrap，再根据我这里的修订步骤对Kickstrap进行Hack。


最近更新
==========

**2012.05.04**

+ 虽然我自己把最新的bootstrap 2.0.3版本修订进来，但这次kickstrap还比较敏捷地集成了进来。不过下次别的插件再更新，我看还是得我们自个儿来更新。

Hack步骤
===========

项目结构调整
-------

+ 我把所有的资源文件夹(css,extras,img,js,less)全部都放到kickstrap这一个文件夹下去了，这样你自己站点的资源文件就可以不必跟kickstrap的混合在一起。build文件夹暂时还没去管。

主题更换
----------

*主要操作是在Less文件夹下面

1. 自己从bootstrap下载最新的bootstrap.less（kickstrap对其做了更改，所以我们用原始版）
2. 自己从http://bootswatch.com/ 下载主题，两个文件，一个bootswatch.less,一个是variable.less
3. 把主题的variable.less直接替换掉bootstrap里（注意如果两者版本不相同，可以自己进行对比Merge，我这里已经Merge好了）。
4. 在bootstrap里加入@import "bootswatch.less";和@import "../extras/settings/overrides.less"; 用来重载
5. kickstrap的"../extras/settings/overrides.less"也有一些bug，几处#gridSystem > .generate(12, 70px, 30px);之类的语法都有错误，如果现在还没更正，可以先注释掉，那几个代码块暂时用不到。
6. 安装nodejs，npm install -g lessc, 然后编译lessc bootstrap.less > bootstrap.css，然后把生成的css放到/kickstrap/css/下就搞定了！


光荣榜
-------
**Mark Otto** (Bootstrap)
+ http://twitter.com/mdo
**Jacob Thornton** (Bootstrap)
+ http://twitter.com/fat
**Adam Kochanowicz** (Kickstrap)
+ http://twitter.com/yourwebsitesUX

