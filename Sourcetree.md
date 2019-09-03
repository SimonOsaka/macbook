## Sourcetree使用
1. 下载Sourcetree mac客户端，当前使用v3.2.1版本。
2. 安装、注册，意外的是不需要注册atlassian账户，而改成注册bitbucket账户，这是可以直接访问的。
3. 注册bitbucket完毕后，打开安装界面，点击登录bitbucket cloud，会在浏览器弹出验证页面，这个过程一去一回就可以完成验证（不过有时候可能需要多操作几次，要有耐心）
4. 验证完成后，其余步骤就不多叙述，一看就懂。
5. 着重说一下如何登录gitlab账户，菜单栏 -> Sourcetree -> 偏好设置... -> 账户 -> 添加...
```
托管主机：Gitlab.com
授权类型：私有Token（灰色不可用）
用户名：登录gitlab.com的用户名
密码：只有一次展示的私有Token
协议：SSH或HTTPS
SSH密钥：id_rsa.pub（选择 协议：SSH 展示，至于SSH密钥如何创建，自行搜索）
```
> 如何创建私有Token？
* 登录gitlab.com
* 用户设置
* Personal Access Tokens
* Add a personal access token
* 勾选需要的项目（可以全部勾选）
* 点击Create personal access token按钮
* 页面顶部出现Your New Personal Access Token，复制，只有一次展示机会，如果找不到，需要重复一遍之前步骤。
