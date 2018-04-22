# 命令行

pwd         查看当前位置  
ls          查看当前位置的文件 不包含隐藏文件  
ls -a       查看所有文件  包含隐藏文件  
ls -A       查看所有隐藏文件 比较-a查看的更多一些 一般不会用到  
clear       清空命令行  
touch 文件名（加上扩展名）      新建文件  
mkdir       创建文件夹 (创建多个加空格)  
cat 文件     查看文件内容  
rm 文件名    删除文件   (rm 文件名 -r  可删除文件夹)(rm -f 强制删除)  
cp 文件名 路径           复制该文件到某个目录下   （-r 复制文件夹）  
cp css/* css1/ -r      将css下所有文件复制到css1 下  
mv 文件或文件夹 目录      移动    (mv file1 file2 重命名)  
git clone 地址 克隆  
cd d: 掉转到D盘  
～主目录  
/根目录  
./当前目录  

git log --pretty=oneline        查看历史版本 每个版本在一行显示  
git reset --hard HEAD^          历史回滚  本地仓库回退到上一个版本 两个^^回退两版本  
git reset --hard HEAD[版本号]    回滚到版本号的版本  
git push -f            强制将本地的版本和网上同步  
git reflog             之前 git 做（记录过）的所有事  
git branch 分支名       新建分支    
git branch             查看本地分支    
git branch -r          查看远端分支  
git branch -a          查看远端和本地分支  
git branch -d 分知名    删除分支  
git branch -b 分知名    新建分支并切换过去  
git checkout 分支名     切换分支    
git merge 分支名        当前所在分支合并其他分支  
git pull origin master 拉取主分支上的更新  当你在自己的分支上想要看主分支上其他同事提交到的更新

主分支上的内容在 新建分支的时候    

本地新建分支之后远端没有分支需要下面命令才能推送到新建的分支上    
git push  -u origin dev    

git status  

## gh-pages

github用户名.github.io 常客 直接访问仓库名 就可以访问index.html  
若想要其他仓库达到同样效果 需要使用gh-pages分支 把需要展示的页面 放到 gh-pages分支下 然后提交之后 访问地址 github  用户名.github.io/仓库名

     git push -u origin gh-pages






#### sudo apt-get install git    安装git  


git add .   
git commit -m'1'  
git push  

## git 记住密码
cd ~  
ls -a  
cat ～/.ssh/id_rsa.pub  
复制密码到github网站 点击头像 settings SSH 添加  
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC///KiMs1KWyMd5IEE3rJC5o9+pqySc5bfQlKb1ZDAqxsyMUfvz4OHtYctIUd3P5ujjM9KM57cTw/0qQuYNhsKXXj+uDuqsHJpmYtYi3WUET3zyS1mKeUxMCYlJprzg6iFI4mKX1mF6Va9AIFiWVBWW7rAUVa4ENALFdzKV33FIgZfPcKN/D1q35bdV7WWA76QIbMxYeg2cJubzfN/LjzK/CBrlRBxE/U1YBFmTciCMf38nbc9koz4RRzjOAB0+hXBY9LGSQP/BTR6vWdWshpbBKensDClbZ7yFTMrMSAlar0jmgffsyDdIUQFcjABoimkyj8Fim7UtbEY2arVSuj7 huangyifei@huangyifei-PC


git init 初始化本地文件夹为 git 仓库  
## 合作
git log 查看提交的版本  
git pull 将远端优先于本地的版本拉取到本地  让远端和本地同步  

linux 系统如何安装 node.js
1.安装curl    sudo apt-get install curl
2.安装 nvm（安装 node 版本管理）     curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash  
3.使用 nvm 安装 node nvm install v8.11.1

npm install jquery --save 使用npm 安装非工具类  
npm install webpack --save-dev 使用 npm 安装工具类 --save-dev可以使用 -D代替




