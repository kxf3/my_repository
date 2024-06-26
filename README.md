Markdown基本语法

1.标题
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
正文。。。。。。。。。。。。。

2.索引（内容目录）

3.强调文本<br/>
**加粗文本**<br/>
__加粗文本2__<br/>
*斜体文本*<br/>
_斜体文本2_<br/>
==标记文本==<br/>
<u>下划线文本</u> <br/>
~~中划线~~<br/>
**粗体和嵌入的_斜体_**<br/>
***全部粗体和斜体***<br/>




4.内容换行、居中
<center>这一行需要居中</center><br/>
若文本有加粗或``则居中无效<br/>
床前明月光，<br/>疑是地上霜<br/>
方法2：使用\，然后接着按下enter<br/>
方法3：输入两个空格，然后按下enter<br/>

5.添加空行
<br/>
<br/>
6.引用

> 引用1
> 引用2
> > 引用2.1
> > > 引用2.1.1
```
what?
```

7.列表<br/>
无序列表：<br/>
- 无序一级列表
	* 无序二级列表
		+ 无序三级列表
- 无序一级列表2


有序列表：<br/>
1. 有序列表1（.和文字之间有一个空格）
2. 有序列表2
3. 有序列表3<br/>hello
4. 有序列表4

列表嵌套：<br/>
1. 列表1
	- 列表1.1
	- 列表1.2
2. 列表2

8.代码块：<br/>
```c
#include<stdio.h>
int main(){
printf("hello");
return 0;
}
```
```bash
ls -a
touch
cd
```
行内代码：<br/>
输出hello world: `printf("hello world")`

9.任务列表<br/>
- [ ] 计划任务
- [x] 完成任务


10.链接<br/>
[链接标题](URL地址 可选title属性)<br/>

[github](https://github.com/ "github网址")<br/>

特例:<br/>
[链接1](https://github.com/)<br/>
[链接2][a]
[a]:https://github.com/
想要链接请点击[此处][a]

11.图片<br/>
![图片名称](图片地址)

12.表格：<br/>
:---为左对齐<br/>
---:为右对齐<br/>
:---:为居中对齐<br/>
|姓名|性别|年龄|
|:---|:---:|---:|
|唐僧|男|34|
|孙悟空|男|200|
|白骨精|女|1000|

13.分割线：<br/>
分割：<br/>
***
分割：<br/>
___

分割：<br/>
---

13.颜色?<br/>

> 字体颜色语法：<font face='黑体' color=#ff0000 size=4>我是正>文</font>
<font face='黑体' color=#ff0000 size=4>我是正文</font>
> 背景颜色：<table><tr><td bgcolor=orange>背景色是：orange</td></tr></table>
<table><tr><td bgcolor=orange>背景色是：orange</td></tr></table>

14.特殊符号<br/>
\\ 表示一个反斜线<br/>
\* 表示一个*<br/>
\{\} 表示{}<br/>

15.文本框<br/>
上面空一行，每行文本前空四个空格

    此处为文本框<br/>
    此处还为<br/>
    ...<br/>

16.注释<br/>
线面一行为注释:<br/>
[//]:注释?


@[TOC](目录)

# github三要素
## Repository仓库
	仓库是github项目管理存储基本单位<br/>
	一个仓库存储一个项目，一个用户可以拥有多个项目，一般仓库分为public、private
## Commit提交
	程序员在整个开发周期，有大量的对代码资源的迭代和修改，都可以通过commit的方式进行记录，便于程序员回溯代码，即使这些代码被删除<br/>
	提交便于使用者观察整个工程的开发流程以及设计流程
## Branch分支
	仓库中可以包含多个分支，分支才是代码文件的第一存储单位，默认仓库主分支为master/main<br/>
	不仅可以管理代码存储，便于多人协作开发
# 仓库内容
1. Code、资源存储、代码资源、二进制、项目管理脚本、许可证等<br/>
2. issues：使用时遇到的bug或进行提交，等待反馈<br/>
3. README:使用markdown语言编写的工程自述文件，包含开发进度、版本更新、使用介绍等
4. LICENSE许可证：GPL2.0/3.0、Apahce2.0、Mit这些许可证，给使用者最大的使用权限以及最少的限制
# Git软件，分布式版本控制系统
仓库管理软件，使用git管理私人代码或企业内容<br/>
一般本地内容新于发布内容<br/>
# 设备认证
## 如何让网站的账户与设备绑定，后续完成代码的管理（上传下载）
git init //创建本地仓库（后续对仓库的操作，都要在仓库位置（master））<br/>
git config --list //查看git的配置文件<br/>
git config --global user.email "邮箱" //绑定邮箱<br/>
git config --global user.name "用户名" //绑定用户名<br/>
ssh-keygen -t rsa -C "注册邮箱" //创建本地密文，记住对应的目录,根据目录查找文件<br/>
rsa.pub文件中复制密文，setting->SSH key and GPG ->new ssh key ->粘贴密文<br/>
ssh -T git@github.com //测试关联是否成功<br/>
## 为目标仓库起别名，定位目标仓库，后续上传都在此仓库
git remote add orgin "ssh地址" //为ssh仓库地址创建别名orgin<br/>
git remote remove orgin //删除orgin别名<br/>
# 本地设备与云端仓库
将code.c放入git缓冲区：git add code.c <br/>
将缓冲区内容放入本地仓库：git commit -m "提交说明" <br/>
将本地仓库文件上传到云端仓库：git push orgin master(上传的本地分支与云端的默认分支一致，合并分支)<br/>
git add //添加内容<br/>
git rm //删除本地文件并删除仓库数据<br/>
git restore //恢复被删除（仓库中还存在才能恢复）<br/>
# 代码更新的依赖关系被破坏
本地内容比云端内容新，完成更新替换；但是如果直接修改云端内容导致本地无法再次提交<br/>
先拉取git pull云端内容，与本地内容合并或操作，而后再次推即可<br/>
git pull --rebase orgin master<br/>
* git rebase --skip //忽略本地内容，保留云端内容<br/>
* git rebase --abort //先将云端复制下来，在用本地替换云端<br/>
* git rebase --continue //合并云端与本地<br/>
# 下载开源代码
git clone "https仓库地址" //下载开源项目的code资源
# 分支Branch
关于分支的相关命令，创建分支，选择分支，合并分支等
# Markdown
github可以编写markdown，文本修饰语言
# 查找关键字
* awesome:去此标签类别中查询项目
* python tutorial：查询资料，书籍，文档
* socket sample：查询对应技术的代码样本
