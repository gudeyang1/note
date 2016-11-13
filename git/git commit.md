对于一般的 `git` 提交, 通常我们会这样做:

    git add .
    git commit -m "添加了 a.html"

有一种比较简单的写法可以合并上面的两种

    git commit -am "添加了 a.html"

>但这种写法存在问题, 它并不能将新创建的文件提交, 比如这样
    
    touch b.html
    git commit -am "添加了 b.html"

此时会报错, 因为这种写法无法将 b.html 添加到暂存区, 所以你还是需要通过下面命令提交 

    git add b.html
    git commit  -m "添加了 b.html"
