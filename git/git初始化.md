当我们安装了git, 需要配置一些环境变量, 环境变量分为三个级别

    系统级别
    用户级别
    项目级别

> 一般情况下我们配置最多的是 `用户级别`

    用户名
    git config --global user.name "Magina BMP"

    用户邮箱
    git config --global user.email "yin32167@aliyun.com"

    列出自己的环境变量
    git config --global list

> 当我们配置了这些环境变量之后, 除了通过 `git config --global list` 查看之外, 还可以通过文件查看

    # mac/linux 
    vi ~/.gitconfig

    # windows
    打开 C:\Users\Magina\.gitconfig (其中Magina为我的用户名)
