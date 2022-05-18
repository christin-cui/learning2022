第一章
    Linux之父 Linus Torvalds，开发出git
    版本控制系统
        集中式
            单一中央服务器：集中存放获取
            协同合作：保存所有修订
            缺点
                需要联网
                服务器单点故障----需要保证服务器的维护良好，磁盘备份


        分布式
            每人电脑都有完整版本库；服务器故障可恢复；不需联网；
            协同合作
                ①同一局域网：给对方推送“修改”
                ②不同局域网：专门服务器保存“修改”



    安装选项教程：https://blog.csdn.net/mukes/article/details/115693833
    相关学习资源
        Git Book
        廖雪峰Git教程
        Git权威指南
        freenode
        Github-cheat-sheet
        动手学Git
        learn git branching


第二章：基础命令
    相关用语
        仓库/版本库（repository）
        ｜ 一个可以被git管理的目录
        跟踪（track）
        暂存（stage）
        提交（commit）
        推送（push）
        拉取（pull）

    支持数据运输协议
        https://
        git://
        SSH

    获取git项目仓库到本地方式
        将尚未进行版本控制的本地目录转换为Git 仓库
            $ cd /D/Automod/my_project
            ｜ 进入项目目录
            $ git init
            ｜ 创建子目录"git"，把目录变成可管理仓库；ls  -ah命令可显示.git
            $ git add file【理解：添加到下一次提交中而不是直接添加到项目中】
            ｜ 跟踪新文件/把已跟踪文件放到暂存区/合并时把有冲突的文件标记为已解决
            ｜ 
            $ git add LICENSE
            $ git commit -m ' message '
            ｜ 文件提交到仓库，-m后是文件提交说明，任意内容

        其它服务器克隆一个已存在的Git 仓库
            $ git clone https://github.com/libgit2/libgit2
            ｜ 克隆git仓库所有数据包括每个文件版本到本地.git文件夹，eg，链接库libgit2
            $ git clone https://github.com/libgit2/libgit2 mylibgit
            ｜ 克隆时自定义本地目录名
            遇到错误：fatal: unable to access 'https://github.com/Jack-Cherish/PythonGame/': OpenSSL SSL_read: Connection was aborted, errno 10053
                解决办法：取消两个代理 
                    git config --global --unset http.proxy 
                    git config --global --unset https.proxy




    记录更新到仓库
        工作目录文件状态
            已跟踪
            ｜ 已纳入版本控制，git已知有记录
                未修改（刚克隆完的仓库文件均属此种）
                已修改
                暂存区

            未跟踪

        检查文件状态
            $ git status
            git status -s 命令或git status --short
            ｜ 输出的格式更紧凑
                 M README
                ｜ 工作区已修改未暂存
                MM Rakefile
                ｜ 修改，暂存后又修改。即有前后版本共存
                --------两栏--------
                A  lib/git.rb
                ｜ 新添加到暂存区
                M  lib/simplegit.rb
                ｜ 已修改已暂存
                ?? LICENSE.txt
                ｜ 未跟踪文件


        文件状态流程
            新文件/未跟踪--（add）--已暂存
            已跟踪文件--（修改）--已修改未暂存--(add)--已暂存
            已暂存①--（修改②）--已修改未暂存（②）&已暂存（原版①）
                需要再次add，才会把修改版②归入已暂存，提交时永远是最后一次add的版本，add后再修改不会被提交


        添加新文件（不会直接跟踪）
            readme文件：$ echo  ' My Project '  > README

        跟踪新文件
            $ git add README

        忽略文件
            创建名为.gitignore的文件，相当于提交黑名单
                格式规范


        后面太多了，直接边看边操作了，没记笔记
        查看修改
        提交更新
        跳过使用暂存区域
        移除文件
        移动文件

    查看提交历史
    撤销操作
        取消暂存文件
        撤销对文件修改

    远程仓库使用
        查看
        添加
        推送
        重命名与移除

    打标签
        列标签
        创建
        附注
        轻量
        后期
        共享
        删除
        检出


