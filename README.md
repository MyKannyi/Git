## GitHub的仓库初始化

```
cd D:/LocalRepository
mkdir Git #创建一个名叫Git的文件夹
cd Git
ls -al
git init #初始化一个空的Git仓库
ls -al #可以发现多了一个.git目录
git config --global user.name "Kannyi"
git config --global user.email "kannyi@foxmail.com"
git config --global --list #查看配置信息
```

**去GitHub上创建一个新的repository：**

![](Images/3.png)

**选择SSH：**

![](Images/4.png)

```
git remote add origin git@github.com:MyKannyi/Git.git #add一个已经存在的仓库到我们的远程仓库，origin是远程仓库的一个代号，不一定要使用origin这个单词，此处我选用Git作为代号，使用命令时必须处于该仓库的路径下！
git remote #验证远程仓库是否添加成功
ssh-keygen -t rsa -C "kannyi@foxmail.com"

#操作：一直回车

cd /Users/kannyi/.ssh #进入之前所提示的路径
ls
cat id_rsa.pub #查看公钥里面有什么内容

#操作：复制公钥的内容
```

![](Images/5.png)

**进入Settings：**

![](Images/6.png)

**创建新的SSH key：**

![](Images/7.png)

**粘贴公钥的内容：**

![](Images/8.png)

```
ssh -T git@github.com #测试一下本地和远程的GitHub是否能成功建立连接

#操作：输入yes

cd D:/LocalRepository/Git #成功通过认证后，返回我们的Git仓库
git push -u origin master #push一个已经存在的仓库到我们的远程仓库
```



## 操作示例

```
cd D:/LocalRepository/Git
git status #发现没有新东西要提交
pwd #查看当前目录

#操作：假设往该文件夹中放了一个新文件learn_git.html

git status #发现有一个未被跟踪的文件learn_git.html
git add learn_git.html
git status
git commit -m "Create learn_git.html" #提交更新并加上注释

#操作：假设对learn_git.html进行了修改

git status
git add . #把所有处于已修改状态的文件移到暂存区
git commit -m "Version 1.0" #提交更新并加上注释
clear #清屏
```

![](Images/1.png)

![](Images/2.png)



## 其他操作

```
git pull origin master #将远程主机的master分支最新内容拉下来，并与本地分支进行合并
```

```
git remote #查看当前的远程仓库
git remote rm Git #移除远程仓库Git
git remote #再次查看，发现远程仓库Git被移除
```

```
git push -f origin master #它会忽略版本不一致等问题，强制将本地库上传到远程库，远程库将会被本地库覆盖，慎用！
```
m
