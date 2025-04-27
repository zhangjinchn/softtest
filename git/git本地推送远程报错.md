git push时出现报错remote: Invalid username or password. fatal: Authentication failed for 'httpremote: Invalid username or password. fatal: Authentication failed for 'http

原因：自从2021年git开始不再接受用户名密码身份登录，可以选择如下方式token认证登录
1、在github生token 个人访问令牌
登录到你的 GitHub 账户。
点击右上角的头像，选择 “Settings”。
在左侧菜单中，点击 “Developer settings”。
选择 “Personal access tokens”，然后点击 “Generate new token”。
为令牌设置一个描述性的名称
设置令牌的过期时间。
点击 “Generate token” 生成令牌。 务必复制并妥善保存生成的令牌，因为你只能看到一次。

2、在 Windows 管理凭证中配置个人访问令牌（token）
打开凭据管理器：单击电脑左下角 “开始” 图标 ，或按下键盘上的 Windows 键打开菜单栏，找到并打开 “控制面板”。在控制面板窗口中，单击 “用户账户和家庭安全” 选项，然后在打开的窗口中点击 “凭据管理器” 。
添加 Windows 凭据：在凭据管理器窗口中，单击 “添加 Windows 凭据” 按钮 。
输入凭据信息：
Internet 地址或网络地址：填写github.com 。
用户名：填写你的 GitHub 用户名。
密码：将你生成的 GitHub 个人访问令牌粘贴在此处 。
保存凭据：输入完成后，单击 “确定” 按钮，即可将个人访问令牌配置到 Windows 管理凭证中。
3、配置 Git 凭证助手
为避免每次操作都输入令牌，可配置 Git 凭证助手来缓存令牌。
在 Windows 上：
bash
git config --global credential.helper wincred
在 macOS 上：
bash
git config --global credential.helper osxkeychain
在 Linux 上：
bash
git config --global credential.helper store
配置后，首次输入用户名和令牌后，Git 会自动保存，后续操作无需再次输入。

