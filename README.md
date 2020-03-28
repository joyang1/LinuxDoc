# Linux 命令手册


## 文件管理
### diff
比较给定的两个文件的不同。

**补充说明**：**diff 命令**在最简单的情况下，比较给定的两个文件的不同。如果使用“-”代替“文件”参数，则要比较的内容将来自标准输入。diff 命令是以逐行的方式来比较文本文件的异同处。如果该命令指定进行目录的比较，则将会比较该目录中的同名文件，而不会对其子目录文件进行任何比较操作。

**语法**

```

diff (选项) （参数）

```

**选项**

```

-<行数>：指定要显示多少行文本。此参数必须与 -c 或 -u 参数一并使用。

```

**参数**

- 文件1：指定要比较的第一个文件；
- 文件2：指定要比较的第二个文件。

**demo**

将目录 `/data/tommy` 下的文件 test.txt 与当前目录下的文件 test.txt 进行比较，输入如下命令：
```

> diff /data/tommy test.txt

```


### diffstat
显示 diff 命令输出内容的柱状图。

**补充说明**：用来显示 diff 命令输出内容的柱状图，用以显示 diff 命令比较两个文件的不同统计信息。用户也可以直接使用`|`将 diff 命令所输出的结果直接送给 diffstat 命令进行统计结果的显示。使用该命令时，如果所比较的文件或者子目录不在当前目录下，则应该使用其完整路径。

**语法**

```

diffstat（选项）（参数）

```

**选项**

```

-n<文件名长度>：指定文件名长度，指定的长度必须大于或等于所有文件中最长的文件名；

-p<文件名长度>：与 -n 参数相同，但此处的<文件名长度>包括了文件的路径；

-w：指定要输出时栏位的宽度；

-v：显示版本信息。

```

**参数**

文件：指定保存有 diff 命令的输出信息文件。

**实例**

将目录”test1“和“test2”下的同名文件“testf.txt”使用 diff 命令将进行比较。然后使用 diffstat 命令对结果进行统计显示，输入如下命令：

```

diff test1 test2 | diffstat

```


### file
用来探测给定文件的类型。

### find
在指定目录下查找文件。

### git
是当下世界上最先进的分布式版本控制系统。相信只要是程序员，没有不知道 git 的。

### ln
用来为文件创建链接。

**补充说明**： **ln 命令**用来为文件创建链接，链接类型分为硬链接和符号链接两种，默认的链接类型是硬链接。如果要创建符号链接必须使用“-s”选项。

**tips**：符号链接文件不是一个独立的文件，它的许多属性依赖于源文件，故而给符号链接文件设置存取权限是没有意义的。

### locate
比 find 更好用的文件查找工具。

### slocate
查找文件或目录。

**补充说明**：用于查找文件或目录。slocate 本身具有一个数据库，里面存放了系统中文件与目录的相关信息。

### lsattr
查看文件的第二扩展文件系统属性。

**补充说明**：用来查看文件的第二扩展文件系统属性。

### mktemp
创建零时文件供 shell 脚本使用。

### mtools
显示 mtools 支持的命令。

### mv
一是用来对文件或目录重命名，二是用来移动文件或目录。

### od
输出文件的八进制、十六进制等格式编码的字节。

**补充说明**： 用于输出文件的八进制、十六进制或其它格式编码的字节，通常用于显示或查看文件中不能直接在终端显示的字符。

### paste
用于合并文件的列，把每个文件以列对列的方式，一列列地加以合并。

### patch
为开放源代码软件安装补丁程序。

**补充说明**：用于为开放源代码软件安装补丁程序。让用户利用设置修补文件的方式，修改、更新原始文件。如果一次仅修改一个文件，可直接在命令列中下达指令依序执行。若配合修订文件的方式则能一次修补大批文件，这也是 Linux 系统核心的升级方式之一。

### rcp
便于在两台 Linux 主机之间进行文件复制操作。

**补充说明**：用于在两台 Linux 主机之间进行文件复制操作。通过适当的配置，在两台 Linux 主机之间复制文件而无需输入密码，就像在本地复制文件一样。

### rm
用于删除给定的文件或目录。

### split
分割任意大小的文件。

**补充说明**：可以将一个大文件分割成许多小文件，常用的比如生成日志，提高文件可读性等。

### tee
从标准输入读取数据并重定向到标准输出和文件。

**补充说明**：主要用途是需要同时查看数据内容并输出到文件时使用。

### touch
创建新的空文件。

**补充说明**：一是用于把已存在文件的时间标签更新为系统当前的时间（默认方式），它们的数据将原封不动地保留下来；二是用来创建新的空文件。大家常用的一般是用来创建新文件。

### umask
- 显示创建文件的权限掩码。
- 通过八进制数的方式设置创建问的权限掩码。
- 通过符号组合的方式设置创建文件的权限掩码。

### whereis
查找二进制程序、代码等相关文件路径。

**补充说明**：whereis 命令只能用于程序名的搜索，而且只搜索二进制文件（参数-b）、man 说明文件（参数-m）、和源代码文件（参数-s），若省略参数，则返回所有信息。

### which
查找并显示给定命令的绝对路径。

### cat

### chattr

### chgrp

### chmod

### chown

### cksum

### cmp

### cp

### cut

### indent


## 文件传输
### bye

### ftp

### ftpcount

### ftpshut

### ftpwho

### ncftp

### tftp

### uucico

### uupick

### uuto

### scp


## 文本处理
### awk

### col

### colrm

### comm

### csplit

### ed

### egrep

### ex

### fgrep

### fmt

### fold

### grep

### ispell

### jed

### joe

### join

### look

### pico

### sed

### sort

### spell

### tr

### uniq

### vi

### wc


## 备份压缩
### ar

### bunzip2

### bzip2

### bzip2recover

### compress

### cpio

### dump

### gunzip

### gzexe

### gzip

### lha

### restore

### tar

### unarj

### unzip

### zipinfo


## 系统管理
### chfn

### chsh

### date

### exit

### finger

### free

### groupdel

### groupmod

### halt

### id

### kill

### last

### lastb

### login

### logname

### logout

### logrotate

### nice

### ps

### pstree

### reboot

### renice

### rlogin

### rsh

### screen

### shutdown

### su

### sudo

### suspend

### tload

### top

### uname

### useradd

### userdel

### usermod

### w

### who

### whoami


## 系统设置
### alias

### bind

### chkconfig

### chroot

### clock

### crontab

### declare

### depmod

### dircolors

### dmesg

### enable

### export

### grpconv

### grpunconv

### hwclock

### insmod

### lilo

### lsmod

### modprobe

### ntsysv

### passwd

### pwconv

### pwunconv

### resize

### rmmod

### rpm

### set

### ulimit

### unalias

### unset


## 网络通讯
### ppp-off

### telnet

### cu

### ip

### ifconfig

### mesg

### nc

### netstat

### ping

### talk

### tcpdump

### traceroute

### write

### arpwatch

### apachectl


## 磁盘管理
### cd

### df

### dirs

### du

### edquota

### eject

### ls

### mkdir

### pwd

### quota

### quotacheck

### quataoff

### quotaon

### repquota

### rmdir

### stat

### tree

### umount


## 磁盘维护
### badblocks

### dd

### e2fsck

### fdisk

### fsck

### hdparm

### losetup

### mkbootdisk

### mke2fs

### mkfs

### mkinitrd

### mkisofs

### mkswap

### swapoff

### swapon

### sync


## 电子邮件与新闻组
### elm

### mail

### mailq

### xlsatoms

### xlsclients

### xlsfonts


