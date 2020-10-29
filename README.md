# phpStudyBackDoor
phpStudy后门检测与利用工具，Python脚本，可一键 GetShell。

## 简述
2019年9月20日，网上传出 phpStudy 软件存在后门，随后作者立即发布声明进行澄清，其真实情况是该软件官网语2016年被非法入侵，然后软件安装包（php_xmlrpc.dll）被植入后门，可进行执行远程命令执行。

此工具为 Python 3 编写，支持单 url 检测和批量 url 检测，以及执行 cmd 命令、一键 GetShell

## 环境
Python 3

pip install requests

## 漏洞检测利用

### 0.帮助

``python phpStudyBackDoor.py -h``

![帮助](https://raw.githubusercontent.com/Writeup001/phpStudyBackDoor/master/image/help.png)


### 1.单 url 检测

``python phpStudyBackDoor.py -u "http://192.168.80.128"``

存在漏洞与不存在漏洞

![](https://raw.githubusercontent.com/Writeup001/phpStudyBackDoor/master/image/vuln.png)
![](https://raw.githubusercontent.com/Writeup001/phpStudyBackDoor/master/image/novuln.png)



### 2.执行 cmd 命令
可执行 Windows 下任意 cmd 命令（前提是开启了 system 函数，默认为开启状态）

``python phpStudyBackDoor.py -u "http://192.168.80.128" --cmdshell``

![](https://raw.githubusercontent.com/Writeup001/phpStudyBackDoor/master/image/cmdshell.png)

### 3.一键 GetShell 
这个可是真的一键 Getshell 不骗人~~

``python phpStudyBackDoor.py -u "http://192.168.80.128" --getshell``
![](https://raw.githubusercontent.com/Writeup001/phpStudyBackDoor/master/image/getshell.png)

### 4.批量 url 检测
对 url.txt 文件中的链接进行批量检测

``python phpStudyBackDoor.py -u "http://192.168.80.128" -f url.txt``
![](https://raw.githubusercontent.com/Writeup001/phpStudyBackDoor/master/image/batch.png)

## 参考引用
https://github.com/theLSA/phpstudy-backdoor-rce

https://github.com/NS-Sp4ce/PHPStudy_BackDoor_Exp
