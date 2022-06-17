## 码云git

#### 本地创建并提交

```java
mkdir wenjianjia
cd wenjianjia
git init
echo "# wenjianjia" >> README.md
git add README.md
git commit -m "first commit"
git remote add origin https://*********.git // git地址
git push -u origin master
```

#### Git 添加一个文件夹, 并推送到远程仓库, 步骤

<font size=4.5 color="violet">**`这里以gitee远程仓库为例`**</font>

#### 在本地仓库先创建一个新文件夹

##### 1.切换到需要git的工程文件夹

```java
$ cd /e/MyJavaProject 
```

##### 2.git init, 将该文件夹变成Git仓库

```java
$ git init
```

##### 3.git add . 将在文件夹所有文件添加

```
$ git add .
```

##### 4.git commit -m “描述内容”, 将文件提交到仓库

```
$ git commit -m "add a Project"
```

##### 5.在码云新建项目

<img src="D:/`Programme_tool/Typora/picture/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L01haWR1b3Vkbw==,size_16,color_FFFFFF,t_70.png" alt="在这里插入图片描述" style="zoom:67%;" />



##### 6.创建本地库和远程库的连接

> <font size=4 color="red">`git remote add origin git@gitee.com/user/MyProject.git`</font> 创建本地库和远程库的连接. 代码中那个的"user" 要改成你自己的啊. 后面那一串就是在码云中新建项目的那个路径, “origin” 这个也是可以改成别的你喜欢的.

```
$ git remote add origin git@gitee.com:user/MyProject.git
```

##### 7.git remote -v 可以查看你刚新建的连接

```
$ git remote -v
```

##### 8.git push origin master , 将本地库推送到gitee

```
$ git push origin master
```

##### 9.问题出现

![在这里插入图片描述](D:/`Programme_tool/Typora/picture/20190920154329315.png)



> 因为在码云上新建项目的时候, 勾选了" 使用Readme文件初始化这个项目 ", 所以会生成一个如下的文件, 而你本地库并没有, 所以出错了. 提示使用 ’ git pull ... ’ 命令…
>
> ![在这里插入图片描述](D:/`Programme_tool/Typora/picture/20190920154424628.png)

##### 10.<font color="viOlet">`git pull --rebase origin master`</font> , 将gitee上的文件和本地库合并.

>
> 合并之后, 你本地库会出现一个如下的文件:
>
> ![在这里插入图片描述](D:/`Programme_tool/Typora/picture/20190920154540752.png)

##### 11.<font color="viOlet">`git push origin master`</font>

```java
$ git push origin master
```

##### 12.公钥添加

> 可能还有公匙的添加, 可以参见 [码云帮助文档](http://git.mydoc.io/?t=180845#text_180845
> ).



## GitHub

### 菜狗新手使用git远程仓库及本地仓库

> ### 1）新建git
>
> ```
> //本地生成一个git版本库
> git init
> ```
>
> ### 2）配置git
>
> ```
> //配置用户名
>  git config --global user.name "你的用户名"
>  //配置邮箱
>  git config --global user.email "你的邮箱"
> ```
>
> ### 3）添加项目到暂存目录，提交项目到本地仓库
>
> ```
> //添加整个项目，（后面是个.点号）
> git add .
> //添加某些个文件用这个命令
> git add [指定目录/文件]
> //提交到本地仓库
> git commit -m "加备注"
> ```
>
> ### 4）推送到远程仓库
>
> ```
> //连接到远程仓库
> git remote add origin https://gitee.com/你的用户名/仓库名.git
> //会报错的话用如下：
> 1、先输入 git remote rm origin
> 2、再输入 git remote add origin https://gitee.com/你的用户名/仓库名.git
> 
> 
> //先将远程仓库拉取下来
> git pull --rebase origin master
> //推送到分支命令
> git push -u origin master
> ```
>
> ### 5）从远程仓库拉取
>
> ```
> git pull origin master
> 
> // 网络超时，error10054；IP地址正确的情况下多传几次；法一
> // 修改设置，解除ssl验证
> git config --global http.sslVerify "false"
> 
> ```
>
> ### 6）回退版本
>
> 



#### 亿些些报错

> github允许你本地仓库有的东西，远程仓库里没有，但**不允许远程仓库有的东西，你本地仓库没有**。
>
> 所以在提交之前需要先拷贝远程仓库，命令如下
>
> ```
> git pull --rebase origin master
> ```
>
> 

三、分支与合并

