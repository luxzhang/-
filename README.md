# Git安装
## 软件清单
* Git-2.18.0-64-bit.exe


## 安装前准备
* 个别电脑之前安装了旧版本的Git，需要先卸载掉

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
