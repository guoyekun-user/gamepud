## 协同开发(版本控制器)

### SVN
1. SVN是集中式服务器，整个公司用的是同一台服务器
2. 服务器端创建仓库
3. SVN客户端操作
    1. 关联服务器端：检出关联
    2. 提交:SVN commit
    3. 更新:SVN update
    4. 冲突：服务器只能基于一个版本进行升级(手动解决)

### Git
Git是分布式服务器，集中式vs分布式
1. 创建仓库(创建版本库)：
    git config --global user.name "Your Name"
    git config --global user.email "email@example.com"
    git init
2. 添加到版本库：
    git add filename
    git commit -m '注释'
3. 版本回退管理：
    git status 查看当前版本库状态
    git diff 查看具体修改内容
    git log 查看历史提交版本信息
    git log --pretty=oneline 查看历史版本信息简约化
    git reset --hard HEAD^  历史版本回退
    git reset --hard 版本号  历史版本回退
    git reflog  记录你的每一次命令
4. 工作区和暂存区、版本库
    工作区：工作目录
    暂存区：git add
    版本库：git commit
5. 管理修改(操作)
6. 撤销修改
    1. 自修改后还没有被放到暂存区  git checkout -- file
    2. 已经添加到暂存区后 git reset HEAD file      git checkout -- file
    3. 已经条件到版本库里 参考版本回退
7. 删除文件
    1. 自然删除，未被添加到版本库：rm file
    2. 已经添加到版本库：
        1. 彻底删除:rm file(右键删除)    git rm file     git commit -m 'remove'
        2. 恢复原样:rm file(右键删除)    git checkout -- file
8. 分支管理
    1. 创建并切换分支: git checkout -b dev
    2. 切换分支: git checkout dev
    3. 查看分支: git branch
    4. 合并分支: git merge dev
    5. 删除分支: git branch -d dev
    6. 创建分支: git branch iwen
    7. 切换分支(新版本): git switch dev
9. 分支解决冲突

10. 关联远程仓库：github
    1. 创建SSH Key：ssh-keygen -t rsa -C "youremail@example.com"
    2. github账号创建SSH Key的关联
    3. 创建仓库，上传本地仓库代码
        1. git remote add origin https://github.com/Geekiwen/web2002.git
        2. git push -u origin master
        3. 修改代码再次上传:git push
11. github的忽略文件

12. 关联远程仓库：gitee(码云)
    1. 创建远程仓库
    2. 克隆远程仓库：git clone url
    3. 添加本地仓库