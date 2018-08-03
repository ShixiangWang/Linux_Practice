常见Linux命令格式：

```
命令名称 [命令参数] [命令对象]
```

常见Linux命令使用查询： <http://man.linuxde.net/>

**习题**：

1. 目录与文本操作

   1. 在家目录下创建目录`file_operation`

   2. 切换到该目录，使用`pwd`命令输出当前目录路径

   3. 分别使用以下几种方式创建文件`a.fasta`：

      1. `echo`命令 + 重定向
      2. `touch`命令 + nano编辑器
      3. vim编辑器

      `a.fasta`内容如下：

      ```
      >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
      ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTID
      FPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREA
      DIDGDGQVNYEEFVQMMTAK*
      ```

   4. 使用`file`命令查看文件信息，使用`cat`命令、`less`命令查看文件内容

   5. 分别使用相对路径和绝对路径的方式列出`file_operation`目录下的文件以及大小

   6. 用vim编辑器重复`a.fasta`文本内容：

      `a.fasta`事后结果应为：

      ```
      >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
      ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTID
      FPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREA
      DIDGDGQVNYEEFVQMMTAK*
      >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
      ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTID
      FPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREA
      DIDGDGQVNYEEFVQMMTAK*
      ```

   7. 将`a.fasta`拷贝为`b.fasta`

   8. 使用`vim`编辑器寻找`b.fasta`第4行中`GQNPTEA`字符，并将其后内存删除并保存

   9. 将`a.fasta`移动到`/tmp`目录

   10. 将`b.fasta`文件压缩为`b.fasta.gz`，压缩级别为8

   11. 解压`b.fasta.gz`

   12. 删除`b.fasta`与`file_operation`目录

   13. 使用`history`命令查看自己完成该练习的过程

   14. 最后删除`b.tar`，利用`man`命令阅读练习中使用过命令的详细说明，比如`man ls`，`man vim`，`man cat`等。

   **参考**：

   ```shell
   wsx@ubuntu18:~$ mkdir ~/file_operation
   wsx@ubuntu18:~$ cd ~/file_operation/
   wsx@ubuntu18:~/file_operation$ echo ">MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken" > a.fasta
   wsx@ubuntu18:~/file_operation$ echo "ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTIDFPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREADIDGDGQVNYEEFVQMMTAK*" >> a.fasta 
   wsx@ubuntu18:~/file_operation$ file a.fasta 
   a.fasta: ASCII text
   wsx@ubuntu18:~/file_operation$ cat a.fasta 
   >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
   ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTIDFPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREADIDGDGQVNYEEFVQMMTAK*
   wsx@ubuntu18:~/file_operation$ ls -lh /home/wsx/file_operation/
   total 4.0K
   -rw-r--r-- 1 wsx wsx 211 8月   2 23:27 a.fasta
   wsx@ubuntu18:~/file_operation$ ls -lh
   total 4.0K
   -rw-r--r-- 1 wsx wsx 211 8月   2 23:27 a.fasta
   wsx@ubuntu18:~/file_operation$ vim a.fasta 
   wsx@ubuntu18:~/file_operation$ cat a.fasta 
   >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
   ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTIDFPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREADIDGDGQVNYEEFVQMMTAK*
   >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
   ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTIDFPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREADIDGDGQVNYEEFVQMMTAK*
   wsx@ubuntu18:~/file_operation$ cp a.fasta b.fasta
   wsx@ubuntu18:~/file_operation$ ls
   a.fasta  b.fasta
   wsx@ubuntu18:~/file_operation$ vim b.fasta 
   wsx@ubuntu18:~/file_operation$ cat b.fasta 
   >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
   ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTIDFPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREADIDGDGQVNYEEFVQMMTAK*
   >MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
   ADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEA
   wsx@ubuntu18:~/file_operation$ mv a.fasta /tmp/
   wsx@ubuntu18:~/file_operation$ gzip -8 b.fasta 
   wsx@ubuntu18:~/file_operation$ gunzip b.fasta.gz 
   wsx@ubuntu18:~/file_operation$ cd ../ && rm -rf file_operation
   wsx@ubuntu18:~/file_operation$ history
   
   ```

   

2. 常用文本处理入门：

   1. 下载所需文件`example.fasta`
   2. 给出该文件的行数、单词数以及字节数
   3. 使用和比较`cat`命令、`less`命令以及`vim`命令查看该文件三种方式的差别，说说自己的理解
   4. 分别输出文件头尾5行的内容
   5. 使用`grep` + `wc`命令统计序列条数、以`chr`为注释头（即`>chr`开头的行以及随后的序列内容行）的序列条数
   6. 使用命令创建文件`chr.fa`，只保留以`chr`作为注释开头的序列（同上）
   7. 比较`chr.fa`与`example.fasta`内容差异
   8. 将`chr.fa`内容的`chr`全部替换为`CHR`
   9. 为`chr.fa`文件添加一列，该列标注所在行号
   10. 仅选出`chr.fa`中包含`chr`的行，给出行号
   11. 去掉`example.fasta`中重复的内容行并按字母升序的顺序输出
   12. 将`example.fasta`与`chr.fa`拼接起来，一是按`example.fasta`的一列内容进行拼接；二是直接将`example.fasta`与`chr.fa`拼接到一起（即将`chr.fa`中的两列变成`example.fasta`的第2与第3列）

3. 生物文本数据处理进阶：

   1. 下载`example.gtf`与`example.bed`、`example.length`

   2. 输出前两个文件大小与行数

   3. 对`example.bed`进行排序，第一列按字符，第二列按数值，检查结果中第1列与第二列排序的差别，为什么？

   4. 将`example.length`中给出的染色体长度信息添加到`example.bed`的第4列，如果没有匹配的染色体长度信息，则保持`example.bed`原3列的结果

   5. 输出`example.gtf`非注释行行数（即以`#`开始的行），如何去除文件中的注释行？

   6. 分别创建`gtf.csv`与`gtf.tsv`文件，存储`example.gtf`中第3到第5列内容，按第3列排序

   7. 输出`gene_id`的唯一值，即输出以下内容的`ENSG*`部分

      ```
      gene_id "ENSG00000223972"
      gene_id "ENSG00000223972"
      gene_id "ENSG00000223972"
      gene_id "ENSG00000223972"
      gene_id "ENSG00000223972"
      ```

   8. 如果想要对某个`gene_id`出现的次数进行计数，该怎么做？

   9. 输出`example.gtf`的第10到1000行

   10. 输出`example.bed`中终止位点大于起止位点10bp的行

   11. 将`gtf`文件`example.gtf`转换为`bed`格式文件`gtf2bed.bed`

   12. 当前`gtf2bed.bed`文件染色体序号是不是没有`chr`前缀？如果没有，请添加

   13. 将`example.gtf`用`gzip`命令压缩

   14. 直接抓取`example.gtf.gz`第9列转录名，例如`ENST00000456328.2_1 `

   15. 如何通过管道命令将以下内容传入为`gtf2bed.bed`头两行？

       ```
       # bed file generated from gtf file
       # generate by <这里填入你的名字>
       ```

       

4. 脚本创建与Shell编程：

   按以下要求创建和完成脚本：

   1. 不能显式地使用`bash`、`sh`运行脚本
   2. 输出系统默认使用的`bash`，系统内核
   3. 输出系统默认的路径
   4. 将脚本文件所在路径添加到环境变量`PATH`中去，并进行判断检查，如果成功加入了则输出`程序路径加入成功！`否则输出`程序路径添加失败！`
   5. 在用户指定路径（输入参数）创建目录`tmp_dir`
   6. 以`a-z`+日期（中间用下划线分隔，比如`a_2018-08-03`）在`tmp_dir`目录中循环创建26个目录，每次创建间隔1秒钟
   7. 检查目录是否创建成功，如果目录存在，输出`创建目录名{此处目录名}成功！`到用户指定路径的`out1`文件中，如果不存在，输出`创建目录名｛此处目录名｝失败！`到用户指定路径的`out2`文件中
   8. 程序退出
   9. 修改脚本权限为`root`可读、可写可执行所有者为可读可写可执行，其他人为不可读不可写只可执行
   10. 指定路径参数运行脚本进行测试

5. 程序/脚本运行与管理： 

   1. 创建脚本进行以下操作：设定变量`N=100`，当`N>1`时，沉睡（N/10）的余数秒，输出该余数秒是多少到当前目录的`s.out`文件中。
   2. 在终端1中修改脚本为可执行，执行该脚本，另开启一个终端2到当前目录，键入`tail -f s.out`，过几秒钟退出第一个终端，观察第2个终端输出还有变化吗
   3. 重新开启一个终端3，输入`jobs -l`命令
   4. 再次运行创建的脚本，运行时在脚本名后加`&`符号，观察运行`tail`命令的终端2，过几秒后退出脚本运行终端3，查看终端2是否还有输出显示
   5. 重复上面的步骤3、4，这次使用`nohup ./脚本名 &`
   6. 杀死运行的脚本
   7. 说说你进行上述操作的体会

6. 系统管理：

   1. 创建新用户`temp`、及其初始密码，家目录

   2. 切换到该用户

   3. 查看当前的网络，说明使用网络的MAC地址、ip地址、网关、DNS等

   4. 以人易读的方式输出系统地内存大小与磁盘大小

   5. 下载当前生信技能树论坛网站<https://vip.biotrainee.com/>内的所有页面

   6. 使用`ps`查看当前的所有进程状态详情

   7. 使用`top`监控进程活动和系统负载信息汇报当前系统的运行时间、进程总数、占用内存和CPU最多的进程

   8. 显示当前系统内存的使用信息

   9. 显示当前登入的用户终端信息，系统的登陆记录

   10. 查询下载生信技能树进程id，杀死该进程

   11. 退出`temp`用户，删除用户及家目录

       

