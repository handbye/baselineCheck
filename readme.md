## linux基线自动化检查脚本

###功能：
- 根据excel表格中的资产信息自动判断操作系统，并使用其中的密码登录
- 自动上传基线检查脚本并执行
- 执行完毕后自动将检查结果下载到本地同时删除之前上传的脚本和存放在服务器端的检查结果

###使用：

```shell
python3 baseline.py -h

usage: baseline.py [-h] -x XLSX -l LFILE [-c COMMAND] [-ld LDIRECTORY]

a baseline check linux_baseline_check

optional arguments:
  -h, --help            show this help message and exit
  -x XLSX, --xlsx XLSX  the target excel path and name
  -l LFILE, --lfile LFILE
                        loacl file or local directory
  -c COMMAND, --command COMMAND
                        command for run check linux_baseline_check, default is
                        "check_server_linux.sh"
  -ld LDIRECTORY, --ldirectory LDIRECTORY
                        save check result to local directory, default is "./"

```

```bazaar
-x 存放资产信息的excel表名称,资产信息需要和test.xlsx中的格式相同
-l 存放基线检查脚本的路径或基线检查脚本名称
-c 执行基线检查脚本的命令，如check_server_linux.sh, 原命令为bash check_server_linux.sh 192.168.1.1 这里只需要输入命令本身即可
-ld 基线检查结果需要下载本地的路径，默认为当前路径（./），如果你使用的是windows系统，这个必须填写
```
###使用演示：

![2019-12-20-15-57-22](https://raw.githubusercontent.com/handbye/images/master/2019-12-20-15-57-22)

###待完善

- 判断资产的用户名和密码是否正确，将不正确的整理到一个表格中
- 一些异常处理使程序更加健壮