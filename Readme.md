# git 基础：
##### 1. 进入存放文件的文件夹并打开 git bash。
##### 2. 输入 git init ----- 初始化空的 git 版本库。
##### 3. 输入 git add "文件名" ----- 把文件上传到 git 列表上。
###### 提示：
* ###### 上传成功不显示任何命令，接着输入命令即可。
##### 4. 输入 git commit "文件名" -m "这里填入描述文件的一些信息" --- 确认把新加入文件的列表提交到 git 服务器上。（如果是首次提交，应该会出现如下问题）
```
      *** please tell me who you are.
      Run
        git config -- global user.eamil "you@example.com"
        git config -- global user.name  "Your Name"
      to set your account's default identity.
      Omit --global to set the identity only in this repository.
      fatal: unable to auto-detect email address (got 'itcast@itcast.(none)')
```
###### 解决方法：
```
      1. 执行：git config -- global user.eamil "you@example.com"
      2. 执行：git config -- global user.name  "Your Name"
      3. 再次执行上面的提交指令即可
```
###### 提示：
* ###### -m "这里填入描述文件的一些信息" ----- 是作为以后出现代码冲突，进行回退的首要理论依据。
* ###### 输入 git status ----- 可查看当前文件夹里未被上传到 git 列表上的文件。
##### 5. 输入 git remote add origin "github 上对应仓库的 URL" ----- 指定 github 上对应的 URL 来关联了本地网络和 git 服务器的一些关系。
#####　6. 输入 git push -u origin master ----- 把要上传的文件真正推送到 git 服务器上。（提交后，会提示如下）
```
      Username for 'https://github.com'：               ---输入注册 github 的 username
      Password for 'https://afei-itcastedu@github.com': ---输入密码
```
###### 解决方法：
```
        按提示依次输入即可。
```       
###### 提示：
* ###### -u ----- 是用来指定当前你选择哪条分支，默认刚创建项目是只有一条分支 master 。

## git 过程中的 bug ：
##### 1. ```! [rejected] master -> master (fetch first)``` ----- 在 push 远程服务器的时候发现出现此错误；原因是没有同步远程的 master，所以我们需要先同步一下 ```git pull origin master``` ，再重新 push 即可。
![git 图片](https://github.com/JackyST0/Markdown/blob/master/bug%201.png)
##### 2. ```error: remote origin already exists.``` ----- 提示远程仓库已存在，我们可以先输入 ```git remote -v``` 来查看远程仓库是否是自己的的仓库，是则可不用理会，否则我们输入 ```git remote rm origin``` 删除关联的 origin 的远程库，然后我们再重新关联上自己仓库即可。
![git 图片](https://github.com/JackyST0/Markdown/blob/master/bug%202.png)


