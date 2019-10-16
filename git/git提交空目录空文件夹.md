**git提交空目录/空文件夹**

git默认不跟踪空目录/空文件夹，如果想跟踪那么就需要添加.gitkeep/.gitignore文件，方法如下：

在项目的目录下执行

```
  find . -type d -empty -exec touch {}/.gitkeep \;
```

命令后所有的空文件夹都会出现*.gitkeep*文件，这时提交到远程仓库就会显示空目录结构。

参考：[ ](https://stackoverflow.com/questions/115983/how-can-i-add-an-empty-directory-to-a-git-repository)[*How can I add an empty directory to a Git repository?*](https://stackoverflow.com/questions/115983/how-can-i-add-an-empty-directory-to-a-git-repository)

