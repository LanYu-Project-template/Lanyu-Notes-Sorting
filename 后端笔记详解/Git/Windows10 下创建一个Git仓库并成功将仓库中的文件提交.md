# Windows10 下使用Git命令篇(一) 创建一个仓库并成功将仓库中的文件提交。

```
1、Github账户设置SSH key
输入ssh-keygen -t rsa -C “邮箱名”，引号内输入注册GitHub绑定的邮箱，然后会有提示操作，直接按回车即可。会生成 .ssh文件，找到文件，用记事本打开id_rsa.pub

2、为github账号配置ssh key
打开GitHub的设置界面，点击SSH and GPG keys，点击new SSH keys，把id_rsa.pub里的内容复制到key里，在Git Bash输入ssh -T git@github.com检查是否绑定成功
```

一、创建一个新的文件夹并进入该文件夹

```
mkdir window中git项目名
cd window中git项目名
```

二、初始化

```
git init

使用 ls -al可以查询目录中多出一个隐藏文件夹 .git
```

三、创建一个文件并增加内容进行提交测试

```
echo '文本内容' > test.txt
git status查看仓库状态
```

四、用 ‘git add .’命令可以将全部有改动的文件保存至暂存区，省去了一个一个输入文件名

```
git add test.txt
git status
```

五、git无法将修改的文件直接提交，每次都要把文件移动至暂存区，在暂存区的文件才可以执行提交。我们继续将这个文件提交。

```
git commit -m 'master简介'  引号内的内容可以随意改动，这个语句的含义是给刚刚上传的文件一个备注。
```

六、git push origin master，应该是直接出现OpenSSH这个界面，失败会让输入GitHub用户名，

```
git config --local user.email 'gitee注册邮箱'
git config --local user.name 'gitee名称'
git config -l
在执行步骤五
git log  查看提交日志
```

七、推送gitee

```
cd window中git项目名
git remote add origin https://github.com/LanYu-Project-template/Lanyu-Notes-Sorting.git
git branch -M main
git push -u origin main
```

八、删除gitee仓库的文件

```
1.clone仓库
  git clone 项目网址

2.cd进入clone下来的仓库，并将gitee仓库上的文件拉下来
  git pull origin main
  
3.查看当前目录，并删除文件
  dir 查看文件

4、删除文件
  rm 删除文件

5.提交删除文件后的仓库
  git commit -m ‘这个文件被删除了’

6.查看仓库的文件
 git push -u origin main
```

