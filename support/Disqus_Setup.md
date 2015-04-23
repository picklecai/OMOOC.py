## 什么是 Disqus ?

Disqus 适用于各式各样的博客平台, 并且易于安装. 有了 Disqus, 所有的人就可以在你的博客或书籍下面评论了.  

------

## 注册Disqus

先去这个[Disqus的官方网址](https://disqus.com)，注册一个账号。

账号注册完以后在右上角有一个齿轮的标记setting，在下拉列表中选择add disqus to site，需要填写Site URL，Site Name，Site Shortname，完事后就注册了一个账号。

这时候网址会自动跳转进<你注册的名字>.disqus.com，这时候，下面的标签页有`comments` `discussions` `analytics` `setting`

- 选择`setting`
- 选择`advanced`
- 在下面的`Trusted Domains`中，添加gitbook.com，gitbooks.io（一行一条网址，不用加www）

----

## 在gitbook中配置Disqus

由于gitbook和github采用版本库相同的办法，所以我们只要把配置文件上传到github里面，然后gitbook自动就会采用这个配置了。

- 新建一个book.json文件
- 输入代码如下：

```
{
    "plugins": [
        "disqus"
    ],
    "pluginsConfig": {
        "shortName": "<你刚才注册的shortName>"
    }
}
```
- 然后将这个book.json文件上传到github的根目录。

## 应该出现的效果
点进去你的书，下面会多一个评论列表。只要注册了Disqus的人，都可以在下面评论。

## Log
- 20150320 tornote发现错误，ccQ修改。
- 20150323 fengguang22 (Issam) 发现'Trusted Domains'其中之一有错误，改为'gitbooks.io'，原文少了's'。
