## gzip ##

是使用广泛的压缩程序，文件经它压缩过后，其名称后面会多出".gz"的扩展名

### 补充说明 ###

**gzip命令** 用来压缩文件。gzip是个使用广泛的压缩程序，文件经它压缩过后，其名称后面会多处“.gz”扩展名。

gzip是在Linux系统中经常使用的一个对文件进行压缩和解压缩的命令，既方便又好用。gzip不仅可以用来压缩大的、较少使用的文件以节省磁盘空间，还可以和tar命令一起构成Linux操作系统中比较流行的压缩文件格式

减少文件大小有两个明显的好处，一是可以减少存储空间，二是通过网络传输文件时，可以减少传输的时间。gzip是在Linux系统中经常使用的一个对文件进行压缩和解压缩的命令，既方便又好用。gzip不仅可以用来压缩大的、较少使用的文件以节省磁盘空间，还可以和tar命令一起构成Linux操作系统中比较流行的压缩文件格式。据统计，gzip命令对文本文件有60%～70%的压缩率。


###  语法

	gzip(选项)(参数)

###  选项

	-a或——ascii：使用ASCII文字模式；
	-d或--decompress或----uncompress：解开压缩文件；
	-f或——force：强行压缩文件。不理会文件名称或硬连接是否存在以及该文件是否为符号连接；
	-h或——help：在线帮助；
	-l或——list：列出压缩文件的相关信息；
	-L或——license：显示版本与版权信息；
	-n或--no-name：压缩文件时，不保存原来的文件名称及时间戳记；
	-N或——name：压缩文件时，保存原来的文件名称及时间戳记；
	-q或——quiet：不显示警告信息；
	-r或——recursive：递归处理，将指定目录下的所有文件及子目录一并处理；
	-S或<压缩字尾字符串>或----suffix<压缩字尾字符串>：更改压缩字尾字符串；
	-t或——test：测试压缩文件是否正确无误；
	-v或——verbose：显示指令执行过程；
	-V或——version：显示版本信息；
	-<压缩效率>：压缩效率是一个介于1~9的数值，预设值为“6”，指定愈大的数值，压缩效率就会愈高；
	--best：此参数的效果和指定“-9”参数相同；
	--fast：此参数的效果和指定“-1”参数相同。
	-num 用指定的数字num调整压缩的速度，-1或--fast表示最快压缩方法（低压缩比），
		-9或--best表示最慢压缩方法（高压缩比）。系统缺省值为6。

###  参数 

- 文件列表：指定要压缩的文件列表。



###  实例

### 1. 将当前目录下的每个文件压缩成.gz文件
	#  gzip *
### 2. 将当前目录下的每个压缩的文件解压，并列出详细信息
	#  gzip -dv *
### 3. 详细当前目录下的压缩文件的信息，但不进行解压
	#  gzip -l *
	详细显示例1中的每个压缩文件的信息，但不进行解压
### 4. 递归的压缩目录
	#  gzip -rv test
	这样所有test下面的文件都变成了*.gz，目录依然存在只是目录里面的文件相应变成了*.gz，这就是压缩，
	和打包不同。因为是对目录操作，所以需要加上-r选项，这样也可以对子目录进行递归了。
	如果要压缩成一个gz文件，可以先用tar命令对目录进行打包，然后再对打包文件使用gzip命令
### 5. 递归的解压目录
	#  gzip -drv   test

### 6. 假设当前目录下有a.txt，b.txt，c.com三个文件，把当前目录下的每个文件压缩成.gz文件。
	#	gzip *

### 7. 将实例一中每个压缩的文件解压，并显示各个文件的压缩比。
	现在是对压缩文件进行解压，可以利用gunzip工具，也可以利用gzip –d。两者在功能上相同，可以根据自己的喜好选择。
	#	gzip -dv *
	#	gunzip -v *
### 8. 详细显实例1中每个压缩文件的信息，但并不解压。
	#	gzip -l *
### 9.压缩一目录。
	假设当前命令下有一目录tst，可以直接将目录下的所有文件进行压缩 
	#	gzip -r tst
	递归压缩目录下的所有文件
	另外一种方法借助tar归档命令，将该目录进行归档整理，然后执行压缩命令 
	#	tar -cf tst.tar tst
	归档software目录。
	#	gzip -v tst.tar
### 10.解压缩当前目录下所有xxx.gz文件，并显示执行的详细过程。

	#	gunzip -v *.gz
### 11.解压缩当前目录下所有xxx.bz2文件。

	#	gunzip -v *.bz2

