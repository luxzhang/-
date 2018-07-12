# Git安装
## 软件清单
* Git-2.16.1.3-64-bit.exe
* NDP452-KB2901907-x86-x64-AllOS-ENU.exe
* SourceTreeSetup-2.4.7.0.exe
* accounts.json

> 安装包目录：Y:\开发团队\01_部门公用文件夹\git软件清单

## 安装前准备
* 个别电脑之前安装了旧版本的Git和SourceTree，需要先卸载掉

## 安装Git
* 默认安装即可
* 安装结束之后，命令行窗口执行 `git --version` 显示git版本号即表示安装成功

## 设置SSH key
1. 命令行窗口执行 `type %userprofile%\.ssh\id_rsa.pub`
1. 如果打印出key值，执行 `type %userprofile%\.ssh\id_rsa.pub | clip`，跳到第8步
1. 如果系统提示找不到文件，则需要生成新的密钥对
1. 任意位置右键，点击 `Git Bash Here`
1. 执行 `ssh-keygen -t rsa -C "your.email@example.com" -b 4096` , **注意替换成你的邮箱**
1. 接着按3次回车
1. 回到Windows命令行窗口，执行 `type %userprofile%\.ssh\id_rsa.pub | clip`，此时key已经复制到粘贴板
1. 打开[http://172.16.1.82/profile/keys](http://172.16.1.82/profile/keys "keys")，黏贴到Key文本框，点击Add key

> 参考链接：[http://172.16.1.82/help/ssh/README](http://172.16.1.82/help/ssh/README "SSH Readme")

# 安装SourceTree（非必选，可用命令行或者开发工具自带的Git客户端替代）
## 安装.net Framework 4.5
* 运行 `NDP452-KB2901907-x86-x64-AllOS-ENU.exe`
* 需要C盘有1G左右的缓存空间，安装成功后实际大小约40M
* 安装过程可能会提示关掉一些进程（如：EPSUI.exe）

## 安装SourceTree
* 地址栏输入%LocalAppData%，回车，创建目录\Atlassian\SourceTree\
* 拷贝 `accounts.json` 文件到%LocalAppData%\Atlassian\SourceTree\
* 点击安装SourceTree
* 到了第3步点击【跳过初始设置】
* 跳过设置ssh密钥
* 跳过安装Mercurial
* 安装成功后将此程序锁定到任务栏

> 备注：如果系统运行着EPSUI.exe，关闭时会提示一个错误

## SourceTree设置SSH key
* 工具->选项->一般->SSH客户端配置
* 设置SSH key，下拉选择OpenSSH，工具自动带入SSH密钥，点击确定即可

## 克隆仓库到本地
* 打开SourceTree，点击Clone
* 源路径填入：git@172.16.1.82:cheney_zhang/test-git.git
* 点击克隆
