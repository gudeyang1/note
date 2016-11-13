首先介绍一下 HEAD 指针

    当前的版本       HEAD
    上一个版本       HEAD^
    上两个版本       HEAD^^
    上三个版本       HEAD^^
    上多个版本       HEAD~n


git revert
---

有时候我们修改了文件, 并且提交了, 但后来发现, 之前做的是对的, 不需要修改, 这个时候我们就需要撤回那次提交.

> 我们先通过git log --oneline 去查看提交的记录

![](http://upload-images.jianshu.io/upload_images/938819-2d60d820f5545b79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 假如我们不想提交style.css, 可以使用 `git revert HEAD~1` 撤销这次提交

![](http://upload-images.jianshu.io/upload_images/938819-b02d370c008264ce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

可以发现, 它会将这条撤回消息的动作也写入提交记录, 并且这次撤回除了影响暂存区和分支, **还会修改工作区**

git reset
---

如果我们想回滚到前面的版本, 比如说添加style.css那个时候, 可以使用git reset, 其中它有三个参数
  
    soft    只改变分支的提交
    mixed   改变分支和暂存区, 不影响工作区
    hard    分支,暂存区和工作区都会影响, 这个操作需要慎重

![](http://upload-images.jianshu.io/upload_images/938819-31b7d91c3f209fc8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 软删除只会移除分支上的提交, 在其之后的修改都会撤回`暂存区`

![](http://upload-images.jianshu.io/upload_images/938819-046fd8061cbfb113.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 混合删除会将其之后的修改全部撤回工作区, 不会影响工作区

![](http://upload-images.jianshu.io/upload_images/938819-111dbe884ebfe3dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 硬删除会将其之后的修改全部撤回, 并且会影响到工作区

    
