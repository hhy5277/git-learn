#learn git
git快速学习指南

##下载git

http://git-scm.com/

windows系统安装教程如下：http://jingyan.baidu.com/article/90895e0fb3495f64ed6b0b50.html

mac系统安装的Xcode就已经带了git，你可以运行终端查看下你的git版本号，命令为：git --version

##配置用户名及密码（前面的$不需要输入）

    $ git config --global user.name "yourname"
    $ git config --global user.email "youremail"

##设置SSH

    $ ssh-keygen -t rsa -C "youremail"
  
按3个回车，密码为空。最后得到了两个文件：id_rsa和id_rsa.pub，我们后面需要的秘钥就在id_rsa.pub这个里面

##在github上添加秘钥

将上面的id_rsa.pub文件中的内容拷贝，注意前后不能有多余的空格，这里要求比较严格。然后在我们的github的用户设置中“SSH key”菜单中，添加我们的秘钥即可。

##git常用操作命令

    git clone git@github.com:marvin1023/git-learn.git     // 克隆某个项目，以该文档为例
    git status                                            // 检查变化 
    git add .                                             // 提交所有的变化文件
    git commit -m '提交说明'                              // 提交确认   并添加关键词
    git pull                                              // 拉取线上的修改文件
    git push origin master                                // 合并进去

上面的"git add ."适用于本地只修改增加文件或文件夹，如果本地执行了删除文件或文件夹那么请使用“git add -A”命令

也可以使用`git commit -a -m 'this is memo'`，直接省略`git add`命令

一般80%的工作都是只用到上面的命令，下面的一些命令如果会了将会更好

    git rm filename                                       // 删除文件
    git rm -r dir                                         // 删除目录
    
    git diff --cached                                     // 修改代码后，查看已修改的内容

    git checkout branchname                               // 切换分支


    git reset --hard HEAD                                 // 撤销到上次提交
    git checkout -- filename                              // 撤销某个文件的修改
    git reset --hard origin/master                        // 放弃本地修改，master表示主，如果是拷贝的其他分支，那么就用分支名
