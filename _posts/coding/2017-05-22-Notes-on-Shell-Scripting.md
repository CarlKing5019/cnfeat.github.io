---
layout: post
title: Notes on Shell Scripting
date: 2017-05-22
categories: Coding
tags: [Linux, macOS, Shell, CLI, Notes]
description: A short note on shell scripting.
---



## Shell 相关命令

1. Shell 文件管理命令
```bash
cd              # 切换目录
ls              # 列出文件(夹)
cp              # 复制文件(夹)
mv              # 移动/重命名文件(夹)
rm              # 删除文件(夹)
pwd             # 显示当前目录
mkdir           # 创建目录
open            # 打开文件
sudo            # 以 root 账号执行命令
echo            # 打印输出
printf          # 格式化打印输出
```


2. 帮助相关命令
```bash
-h              # 打开命令自带帮助
--help          # 打开命令自带帮助
man             # 打开 man 文档
info            # 打开 info 文档
help            # 等同于 --help
which           # 显示脚本位置或函数定义或别名定义
mandoc          # 以 pdf 格式查看 man 帮助文档
```


3. 查看文件相关命令
```bash
open            # 用默认应用打开文件或网址
show            # 快速预览文件, defined by me
img             # 在终端打开图片, need imgcat
cat
less
more
head
tail
```


4. 字符处理相关命令
```bash
sed
awk
grep
sort
uniq
cut
tr
paste
split
```


5. Shell 配置相关命令
```bash
history         # 打印输出历史命令
alias           # 设定别名
unalias         # 取消别名
function        # 定义函数
source          # 读取并执行脚本, 简写为 .
~/.profile      # shell 配置文件, 多个 shell 共用
~/.bash_profile # bash 配置文件
~/.zshrc        # zsh 配置文件
```


## Shell 相关程序

1. 安装软件相关程序
```bash
brew            # macOS package manager
pip             # python package manager
npm             # nodejs package manager
gem             # ruby package manager 
```


2. 一些非常有用的 Linux 程序
```bash
git             # 版本管理, 配合 sourcetree 使用更方便
make            # 自动化编译, makefile for latex, markdown
pandoc          # 文档转换器, 支持 md, latex, html, pdf 等
wget            # 用于下载
curl            # 用于下载
```


3. 我写的一些函数/脚本
```bash
fy              # 中英翻译
help            # 等价于 --help
makepdf         # 转换 tex/md/tm/wiki 等为 pdf
mandoc          # 在预览中打开 man 文档
show/ql         # 预览文件, 等同于空格键
```


4. 其他常用的一些命令
```bash
texdoc          # 查看 LaTeX 帮助文档
chmod a+x       # 设置可运行权限
ping            # 检查网络连接
du -sh          # 显示文件夹大小
unzip           # 解压缩文件
say             # 朗读文字
pbcopy          # 复制到剪切板
pbpaste         # 读取剪切板
```

5. 当你在程序中迷失了方向时, 请使用以下命令
```bash
whoami          # 我是谁
where           # 我在哪里
whatis          # = man -f
whereis         # = which -a
```


6. oh-my-zsh macos 插件 OSX 提供的命令, 源码见于 [GitHub](https://github.com/robbyrussell/oh-my-zsh/blob/master/plugins/osx/osx.plugin.zsh).
```bash
tab             # 在一个新标签打开当前目录;
cdf             # cd 到当前 Finder 打开的目录;
itunes          # 命令行操作 iTunes;
quick-look      # = show/ql, 快速查看文件, 类似于空格键;
man-preview     # = mandoc, 在预览中打开 man 帮助文档.
```



## Shell 语法知识

1. Shell 通配符
```bash
?               # 匹配任意一个字符
*               # 匹配任意 0 个或多个字符
[list]          # 匹配 list 中的任意一个字符
[!list]         # 匹配 list 之外的任意一个字符
[c1-c2]         # 匹配 c1-c2 中的任意一个字符
{s1,s2,...}     # 匹配 s1, s2 或 ... 中的一个字符串
```


2. Shell 元字符
```bash
=               # 设定变量(注意等号两边不要有空格)
;               # 按顺序执行命令
&&              # 若前者返回 true, 则继续执行后续命令
||              # 若前者返回 false, 则继续执行后续命令
$()             # 命令替换
${}             # 变量替换
|               # 命令管道
``              # 命令替换, 推荐使用 $()
<               # 重定向 stdin
>               # 重定向 stdout
>>              # 追加到文件
2>              # 重定向 stderr
&>              # 重定向 strout 和 stderr
```


3. Shell 转义符
```bash
''              # 硬转义, 关闭所有的元字符, 通配符
""              # 软转义, 只允许 $ 和 ` 做变量和命令替换
\               # 转义, 转义其后的通配符和元字符
```


4. Shell 脚本中的变量
```bash
$#              # 传递给函数的参数个数
$*              # "$*"="$1c$2c$3c...", 是一个字符串, 其中 c 表示 ${IFS} 的第一个字符
$@              # "$@"=$@=$*="$1" "$2" "$3" ..., 是多个字符串
$n              # 传递给函数的第 n 个参数
$?              # 显示最后命令的退出状态, 0 表示没有错误
```


5. 终端中的变量
```bash
!!              # 上一条命令
!*              # 上一条命令的所有参数
!^              # 上一条命令的第一个参数
!$              # 上一条命令的最后一个参数
!:-             # 上一条命令中除了最后一个参数的部分
!!:gs/1/2       # 将上一条命令中的 1 替换为 2
```


6. 控制流
```bash
if
elif
else
case
for
while
until
test
```



