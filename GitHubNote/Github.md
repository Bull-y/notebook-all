
## GitHub
1. **大方框区域**就是项目的所有源代码，点击某个文件就可以看到**源码内容**
2. 源码的下面会自动显示`readme.md`文件，是**项目的说明文件**
3. `Code-DownLoadzip`将源码打包下载
   - 下载源码不需要登录
   - 登录后点击右上角`fork`，可以将代码复制到自己的空间内
4. readme.md也可以拿**记事本**打开
5. 点击作者头像，repositories(仓库)，多少就是多少个项目
   - 下面显示什么语言写的、有多少人点赞、最后一次更新时间
6. 搜索栏两行一个是当前作者，一个是整个github
   - 还可以通过编程语言进一步筛选
7. 右上角`+`---`new repository`---新存储库
   - 简介中使用汉字，方便华人搜索和阅读
   - 勾选read.me(对新手来说，默认很合适)
   - `add file`
8. 留言相关
   - issue：问题/话题/议题
   - 标题-正文-发送
9. `commit`旁边那七个数字字母是哈希值，可以看commit的具体信息
    - 红的是以前的，绿的是新改的
10. 分支的话，所有的分支代表不同的功能，最后都会合到一个main分支里。
11. lisence如果不是mit，那么可能涉及版权问题；
    - mit就是你要指明一下作者就行，就可以随便用
12. 搜索tip:
    - 找百科大全 awesome xxx
    - 找项目  xxx sample 
    - 找项目空架子 xxx starter / xxx boilerplate 
    - 找教程 xxx tutorial

## Git
1. Git是一个运行在你电脑上的版本控制软件，而GitHub是基于Git这个版本控制软件打造的网站
2. Git有三个概念：提交commit,仓库repository,分支branch
    - **提交commit：** 以提交为单位记录下来，每次提交都有保存
    - **仓库repository：** 每个代码文件夹也可以是一个仓库，每一次更改代码就会被控制记录下来
    - **分支branch：** 不同的人不同的需求在当前代码开辟不同的分支，各写各的，最后合起来
3. 下载Git的网站：
   ```
   https://registry.npmmirror.com/binary.html?path=git-for-windows/
   ```
4. 怎么下载项目
   - 点击GitHub的Code，复制它的HTTPS的地址
   - 进入要放置项目的文件夹中，右键，gitbash here
   - ` git clone xxxx`其中`xxxx`代表HTTPS的地址
   - GitHub的`star`也可以将项目进行软性收藏
5. `download-zip`下载下来是一个文件夹；`git clone`下载下来是一个仓库
   - 文件夹->仓库 : 初始化
     - 在文件夹中打开 `git bash here`
     - `git init`
     - 之后就会多个`.git`的文件夹，说明变成了一个仓库
6. 变成仓库之后用vscode打开就可以在终端进行git了
7. vscode中三个点代表终端，有点分支的意思
   - 更改文件夹代表着你现在git已有的东西进行比较
   - 然后把这次的变化标注给你，U代表着完全新增的文件
   - 这是vscode对git的集成
8. 工作区----(`git add<file>`)----暂存区(`git commit`)----仓库
9. 将所有工作区提交到仓库的步骤：
    - 先提交到暂存区 `git add -A`，然后`U`就会变成`A`
    - 会多一个文件夹叫做暂存的更改
    - 更改的文件就空了
    - 然后输入邮箱和名字`git config --global user.email "171450290@qq.com" ` `git config --global user.name "zp"`
    - 然后进行放置仓库`git commit -m "first commit"`
10. 9的另一种方法(不用命令)：
    - 可以在更改文件夹的单个文件旁边点`+`，也可以在更改文件夹旁边点`+`将所有文件添加进去
    - 在上面输入信息`first commit`,然后`ctrl+enter`
    - 至此仓库就提交上去了
11. git log --stat
    - 每一个commit 会有一个哈希值，每个commit是唯一的，用于指定每个commit
    - 作者，时间 
    - 这个命令行还是很蹩脚的
    - 直接在commits里面看就行
12. `git checkout <xxx>` xxx为文件名（还没有提交）
    - 将更改里的xxx.md打回去
    - 也就是在工作区打回去
    - **可以直接在更改里点撤回！**
13. `git reset HEAD^`（已经提交了）
    - 功能是：提交了后在Commits区打回去
    - 但是**可以直接在Commits中撤回！ 然后xxx.md就回到更改文件里了，然后调用12功能，或者直接撤回**
    - (2)再化简就是**以上可以直接右键UnDo，然后会在暂存区，再按`-`就回到了工作区。**
14. 分支：让不同的人之间能够相互协作
    - 每个仓库初始化后都会有个主分支，主分支必须是一个完成态(是可以跑的)
    - 他是一切分支的起点和终点，所以是长周期的项目话一定要用分支
    - `git checkout -b a` 在当前节点建立一个分支
    - `git checkout master`重回master分支
    - 
    - 
## 其他资源
1. 找开源项目
   - https://github.com/trending/
   - https://github.com521xueweihan/HelloGitHub
   - https://github.com/ruanyf/weekly
   - https://www.zhihu.com/column/mm-fe
   - 我是a同学写的话


## 要掌握的
1. git clone 
2. star
3. readme.md
4. issue
5. license
6. git add -A
7. git config --global user.email "171450290@qq.com
8. git config --global user.name "zp"
9. git commit -m "xxx" xxx为信息
10. git log --start
11. git checkout -b <branchname>
