> Fork是一款免费的git图形客户端，功能强大。由于sourcetree使用的时候需要注册一个账号，一直无法注册，就改使用了Fork，没想到还有意外收获🙂。

1. 点击菜单`File - New Tab`可以切换不同的仓库。
2. 点击菜单`File - Clone…`克隆***.git仓库代码。
3. 点击菜单`Repository`有git最基本常用的操作。
4. 菜单`Respository - Git Flow`提供git flow流程化操作。
5. 菜单`Repository - Git LFS`提供大文件处理方式。
6. 主界面左侧有五个栏目

```javascript
All - 展示所有仓库
Recent - 最近使用的仓库
Bitbucket - Bitbucket登录仓库、展示账户信息
GitHub - GitHub登录仓库、展示账户信息
GitLab - GitLab登录仓库、展示账户信息
```

7. 主界面All模式，中间展示仓库列表，双击已经clone完成的仓库进入
8. 仓库内

```javascript
左侧 - 仓库的基本结构，可以用鼠标右键点击执行操作
右侧(上) - git log记录，可以用鼠标右键点击执行操作
右侧(下) - 点击git log记录后，展示响应的信息(Commit当时提交文件，Changes当时提交文件改变内容对比，File Tree当时提交的文件树)
```

9. 使用pull request

> 可以发起代码合并申请，让审核代码人进行review

```markdown
仓库内
左侧
1. 展开Remotes
2. 右键点击要发起pull request的分支
3. 点击Create Pull Request on GitHub.com...
4. 在弹出框内点击Send Pull Request
5. OK
```

