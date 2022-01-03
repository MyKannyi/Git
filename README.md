cd D:/LocalRepository
mkdir Git
cd Git
ls -al
git init #初始化了一个空的Git仓库
ls -al #可以发现多了一个.git目录
git config --global user.name "Kannyi"
git config --global user.email "kannyi@foxmail.com"
git config --global --list #查看配置信息
git status #发现没有新东西要提交
pwd
#假设已经往该文件夹中放了一个新文件夹Images
git status #发现有一个未被跟踪的文件
git add Images
git status
git commit -m "Create Images" #每一次更新的注释
#假设已经对Images的内容进行了修改
git status
git add . #把所有处于已修改状态的文件移到暂存区
git commit -m "Update Images" #每一次更新的注释
clear
---------------------------------------------------
git remote add origin git@github.com:MyKannyi/Git.git #origin是远程仓库的一个代号，不一定要使用这个单词，使用命令时必须处于该仓库的路径下！
git remote #验证远程仓库是否添加成功
ssh-keygen -t rsa -C "kannyi@foxmail.com"
#操作：一直回车
cd /c/Users/Kannyi/.ssh #上面提示的路径
ls
cat id_rsa.pub #查看公钥里面有什么内容
#操作：复制
ssh -T git@github.com #测试一下本地和远程的GitHub是否能成功建立连接
#输入yes
cd D:/LocalRepository/Git #成功通过认证后，切换回我们的Git仓库
git push -u origin master #push一个已经存在的仓库到我们的远程仓库
