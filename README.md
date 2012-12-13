宗旨
========

Kickstrap（内置bootstrap）是超屌的快速构建HTML5应用的前端框架集大成者，他基于bootstrap加入了主题功能，HTML5Boilerplate，IE6兼容插件，和各种酷炫插件，特别是图标采用了font-awesome。

然而由于项目元素较多，文档不够详尽，目前使用起来有些不便之处，这里根据我的实际运营的项目，对它进行一些修订，这里专门刊出与主项目不同之处，所以在使用时，先下载Kickstrap，再根据我这里的修订步骤对Kickstrap进行Hack。

**最近更新**
+ 2012.12.14 bootstrap和kickstrap都加快了开发脚步, 现在再看一眼时bootstrap已经2.2.2,kickstrap也发布了1.2Beta, 包含2.2.1的bootstrap, 可用性大大提高, 以至于我这个Kickstrap0.9改良版已经没有永无之地了, 所以请大家还是关注kickstrap吧, 1.0以后已经开始逆天了

+ 2012.06.20 更新至bootstrap/bootswatch 2.0.4; font-awesome 2.0重大版本更新

+ 2012.05.04 集成bootstrap 2.0.3, bootswatch 2.0.3(kickstrap插件很多，有时我们需要新插件的特性，kickstrap更新没那么及时，我们得自个儿来更新。)

Hack步骤
===========

项目结构调整
-------------

+ 我把所有的资源文件夹(css,extras,img,js,less)全部都放到kickstrap这一个文件夹下去了，这样你自己站点的资源文件就可以不必跟kickstrap的混合在一起。build文件夹暂时还没去管。

主题更换
----------

+ 主要操作是在Less文件夹下面

1. 自己从bootstrap下载最新的bootstrap.less（kickstrap对其做了更改，所以我们用原始版）
2. 自己从http://bootswatch.com/ 下载主题，两个文件，一个bootswatch.less,一个是variable.less 
2.1 PS: *这里使用的是United主题，如果想用别的主题，使用相应主题的这两个文件即可; 另外如果不想web加载google字体，在bootswatch.less里面把文件头里的import注释掉。
3. 把主题的variable.less直接替换掉bootstrap里（注意如果两者版本不相同，可以自己进行对比Merge，我这里已经Merge好了）。
4. 在bootstrap里加入@import "bootswatch.less";和@import "../extras/settings/overrides.less"; 用来重载
5. kickstrap的"../extras/settings/overrides.less"文件末尾的"import theme"注释掉，因为我们已经自制主题，也可能有一些bug导致编译不过，比如1.0RC版本里几处#gridSystem > .generate(12, 70px, 30px);之类的语法都有错误，如果现在还没更正，可以先注释掉，那几个代码块暂时用不到。
6. 安装nodejs，npm install -g lessc, 然后编译lessc bootstrap.less > bootstrap.css，然后把生成的css放到/kickstrap/css/下就搞定了！

+ 更新font-awesome

1. 直接更新font-awesome的四个font文件
2. 更新less，注意font路径
3. IE7: 不需要在kickstrap的override里引入ie7.less，因为这个fix是一个单独的css fix，只需要把css复制过来，
<!--[if IE 7]><link rel="stylesheet" href="assets/css/font-awesome-ie7.css"><![endif]-->

光荣榜
========
+ **Kickstrap** http://ajkochanowicz.github.com/Kickstrap/
+ **Bootswatch** http://bootswatch.com/
+ **Mark Otto** (Bootstrap) http://twitter.com/mdo
+ **Jacob Thornton** (Bootstrap) http://twitter.com/fat
+ **Adam Kochanowicz** (Kickstrap) http://twitter.com/yourwebsitesUX

