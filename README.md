`Linux 命令手册`

# 文件管理
## diff
比较给定的两个文件的不同。

### 补充说明
**diff 命令**在最简单的情况下，比较给定的两个文件的不同。如果使用“-”代替“文件”参数，则要比较的内容将来自标准输入。diff 命令是以逐行的方式来比较文本文件的异同处。如果该命令指定进行目录的比较，则将会比较该目录中的同名文件，而不会对其子目录文件进行任何比较操作。

### 语法

```

diff (选项) （参数）

```

### 选项

```

-<行数>：指定要显示多少行文本。此参数必须与 -c 或 -u 参数一并使用。

```

### 参数

- 文件1：指定要比较的第一个文件；
- 文件2：指定要比较的第二个文件。

### 实例

将目录 `/data/tommy` 下的文件 test.txt 与当前目录下的文件 test.txt 进行比较，输入如下命令：
```

> diff /data/tommy test.txt

```


## diffstat
显示 diff 命令输出内容的柱状图。

### 补充说明
用来显示 diff 命令输出内容的柱状图，用以显示 diff 命令比较两个文件的不同统计信息。用户也可以直接使用`|`将 diff 命令所输出的结果直接送给 diffstat 命令进行统计结果的显示。使用该命令时，如果所比较的文件或者子目录不在当前目录下，则应该使用其完整路径。

### 语法

```

diffstat（选项）（参数）

```

### 选项

```

-n<文件名长度>：指定文件名长度，指定的长度必须大于或等于所有文件中最长的文件名；

-p<文件名长度>：与 -n 参数相同，但此处的<文件名长度>包括了文件的路径；

-w：指定要输出时栏位的宽度；

-v：显示版本信息。

```

### 参数
文件：指定保存有 diff 命令的输出信息文件。

### 实例

将目录”test1“和“test2”下的同名文件“testf.txt”使用 diff 命令将进行比较。然后使用 diffstat 命令对结果进行统计显示，输入如下命令：

```

diff test1 test2 | diffstat

```

`注意`：使用这条命令可以非常方便地实现统计显示的功能。

对于查看文件中的内容，用户可以通过 cat 命令进行查看即可，具体操作如下：

```

cat test1/testf.txt

```


## file
用来探测给定文件的类型。

### 补充说明

用来探测给定文件的类型。file 命令对文件的检查分为文件系统、魔法幻数和语言检查 3 个过程。

### 语法
```

file（选项）（参数）

```

### 选项

```

-b：列出辨识结果时，不显示文件名称；
-c：详细显示指令执行过程，便于排错或分析程序执行的情形；
-f<文件名称>：指定名称文件，其内容有一个或多个文件名称时，让 file 依序这些文件，格式为每列一个文件名称；
-L：直接显示符号链接所指向的文件类别；
-m<魔法数字文件>：指定魔法数字文件；
-v：显示版本信息；
-z：尝试去解读压缩文件的内容。

```

### 参数

文件：要确定类型的文件列表，多个文件之间使用空格分开，可以使用 shell 通配符匹配多个文件。

### 实例

显示文件类型


## find
在指定目录下查找文件。

### 补充说明

用来在指定目录下查找文件。任何位于参数之前的字符串都将被视为欲查找的目录名。如果使用该命令时，不设置任何参数，则 find 命令将在当前目录下查找子目录与文件。并且将查找到的子目录和文件全部进行显示。

### 语法
```

find （选项）（参数）

```

### 选项
```

-amin<分钟>：查找在指定时间内曾被存取过的文件或目录，单位以分钟计算；
-anewer<参考文件或目录>：查找其存取时间较指定文件或目录的存取时间更接近现在的文件或目录；
-atime<24小时>：查找在指定时间曾被存取过的文件或目录，单位以 24 小时计算；
-cmin<分钟>：查找在指定时间之时被更改过的文件或目录；

```

### 参数

起始目录：查找文件的起始目录。

### 实例
```

# 当前目录搜索所有文件，文件内容包含 “10.23.23.23”的内容
find . -type f -name "*" | xargs grep "10.23.23.23"

```


## git
是当下世界上最先进的分布式版本控制系统。相信只要是程序员，没有不知道 git 的。

### ln
用来为文件创建链接。

### 补充说明

**ln 命令**用来为文件创建链接，链接类型分为硬链接和符号链接两种，默认的链接类型是硬链接。如果要创建符号链接必须使用“-s”选项。

**tips**：符号链接文件不是一个独立的文件，它的许多属性依赖于源文件，故而给符号链接文件设置存取权限是没有意义的。

### 语法

```

ln [选项] ... [-T] 目标 链接名   （第一种格式）
ln [选项] ... 目标              （第二种格式）
ln [选项] ... 目标 ... 目录      （第三种格式）
ln [选项] ... -t 目标 目标 ...    (第四种格式) 

```

### 选项

```

--backup[=CONTROL] 为每个已存在的目标文件创建备份文件
-b 类似 --backup，但不接受任何参数
-d， -F， --directory 创建指向目录的硬链接（只适用于超级用户）
-f， --force  强行删除任何已存在的目标文件

```

### 参数

- 源文件：指定链接的源文件。如果使用`-s` 选项创建符号链接，则源文件可以是文件或目录。创建硬链接时，则源文件只能是文件。
- 目标文件：指定源文件的目标链接文件。

```

none, off        # 不进行备份（即使使用了 --backup 选项）
numbered, t      # 备份文件加上数字进行排序
existing, nil    # 若有数字的备份文件已经存在则使用数字，否则使用普通方式备份。
simple, never    # 永远使用普通方式备份

```

### 实例

将目录 `/data/tommy/test1` 下的文件 t1.c 链接到目录 `/data/tommy/test2` 下的文件 t2.c。

```

cd /data/tommy/
ln /test1/t1.c /test2/t2.c

```

在执行 ln 命令之前，目录 `/data/tommy/test2` 中不存在 test2.c 文件。执行 ln 之后，在 `/data/tommy/test2` 目录中才有 test2.c 文件，表明 test1.c 和 test2.c 链接起来（注意，二者在物理上是同一文件），利用 `ls -l` 命令可以看到链接数的变化。

在目录 `/data/tommy/test2` 下建立一个符号链接文件 test2-1.c，使它指向目录 `/data/tommy/test3`。

```

ln -s /data/tommy/test3 /data/tommy/test2/test2-1.c

```

执行完该命令后，`/data/tommy/test3` 代表的路径将存放在名为 `/data/tommy/test2/test2-1.c` 的文件中。



## locate
比 find 更好用的文件查找工具。

### 补充说明

locate 让使用者可以很快速的搜寻档案系统内是否有指定的档案。其方法是先建立一个包括系统内所有档案名称及路径的数据库，之后当寻找时就只需查询这个数据库，而不必实际深入档案系统之中了。在一般的 distribution 之中，数据库的建立都被放在 crontab 中自动执行。

## slocate
查找文件或目录。

### 补充说明
用于查找文件或目录。slocate 本身具有一个数据库，里面存放了系统中文件与目录的相关信息。

## lsattr
查看文件的第二扩展文件系统属性。

### 补充说明
用来查看文件的第二扩展文件系统属性。


## mktemp
创建零时文件供 shell 脚本使用。

## mtools
显示 mtools 支持的命令。

## mv
一是用来对文件或目录重命名，二是用来移动文件或目录。

## od
输出文件的八进制、十六进制等格式编码的字节。

### 补充说明
用于输出文件的八进制、十六进制或其它格式编码的字节，通常用于显示或查看文件中不能直接在终端显示的字符。

## paste
用于合并文件的列，把每个文件以列对列的方式，一列列地加以合并。

## patch
为开放源代码软件安装补丁程序。

### 补充说明
用于为开放源代码软件安装补丁程序。让用户利用设置修补文件的方式，修改、更新原始文件。如果一次仅修改一个文件，可直接在命令列中下达指令依序执行。若配合修订文件的方式则能一次修补大批文件，这也是 Linux 系统核心的升级方式之一。

## rcp
便于在两台 Linux 主机之间进行文件复制操作。

### 补充说明
用于在两台 Linux 主机之间进行文件复制操作。通过适当的配置，在两台 Linux 主机之间复制文件而无需输入密码，就像在本地复制文件一样。

## rm
用于删除给定的文件或目录。

## split
分割任意大小的文件。

### 补充说明
可以将一个大文件分割成许多小文件，常用的比如生成日志，提高文件可读性等。

## tee
从标准输入读取数据并重定向到标准输出和文件。

### 补充说明
主要用途是需要同时查看数据内容并输出到文件时使用。

## touch
创建新的空文件。

### 补充说明
一是用于把已存在文件的时间标签更新为系统当前的时间（默认方式），它们的数据将原封不动地保留下来；二是用来创建新的空文件。大家常用的一般是用来创建新文件。

## umask
- 显示创建文件的权限掩码。
- 通过八进制数的方式设置创建问的权限掩码。
- 通过符号组合的方式设置创建文件的权限掩码。

## whereis
查找二进制程序、代码等相关文件路径。

### 补充说明
whereis 命令只能用于程序名的搜索，而且只搜索二进制文件（参数-b）、man 说明文件（参数-m）、和源代码文件（参数-s），若省略参数，则返回所有信息。

## which
查找并显示给定命令的绝对路径。

## cat
连接多个文件，并打印到标准输出。
### 语法

```
cat [OPTION]... [FILE]...

```

### 主要用途

## chattr

## chgrp

## chmod

## chown

## cksum

## cmp

## cp

## cut

## indent


# 文件传输
## bye

## ftp

## ftpcount

## ftpshut

## ftpwho

## ncftp

## tftp

## uucico

## uupick

## uuto

## scp


# 文本处理
## awk

## col

## colrm

## comm

## csplit

## ed

## egrep

## ex

## fgrep

## fmt

## fold

## grep

## ispell

## jed

## joe

## join

## look

## pico

### sed

## sort

## spell

## tr

## uniq

## vi

## wc


# 备份压缩
## ar

## bunzip2

## bzip2

## bzip2recover

## compress

## cpio

## dump

## gunzip

## gzexe

## gzip

## lha

## restore

## tar

## unarj

## unzip

## zipinfo


# 系统管理
## chfn

## chsh

## date

## exit

## finger

## free

## groupdel

## groupmod

## halt

## id

## kill

## last

## lastb

## login

## logname

## logout

## logrotate

## nice

## ps

## pstree

## reboot

## renice

## rlogin

## rsh

## screen

## shutdown

## su

## sudo

## suspend

## tload

## top

## uname

## useradd

## userdel

## usermod

## w

## who

## whoami


# 系统设置
## alias

## bind

## chkconfig

## chroot

## clock

## crontab

## declare

## depmod

## dircolors

## dmesg

## enable

## export

## grpconv

## grpunconv

## hwclock

## insmod

## lilo

## lsmod

## modprobe

## ntsysv

## passwd

## pwconv

## pwunconv

## resize

## rmmod

## rpm

## set

## ulimit

## unalias

## unset


# 网络通讯
## ppp-off

## telnet

## cu

## ip

## ifconfig

## mesg

## nc

## netstat

## ping

## talk

## tcpdump

## traceroute

## write

## arpwatch

## apachectl


# 磁盘管理
## cd

## df

## dirs

## du

## edquota

## eject

## ls

## mkdir

## pwd

## quota

## quotacheck

## quataoff

## quotaon

## repquota

## rmdir

## stat

## tree

## umount


# 磁盘维护
## badblocks

## dd

## e2fsck

## fdisk

## fsck

## hdparm

## losetup

## mkbootdisk

## mke2fs

## mkfs

## mkinitrd

## mkisofs

## mkswap

## swapoff

## swapon

## sync


# 电子邮件与新闻组
## elm

## mail

## mailq

## xlsatoms

## xlsclients

## xlsfonts


