---
show: step
version: 1.0
enable_checker: true
---

# 牛说(cowsay)

## 回忆上次内容

- 我们狂飙了一路
  - 从用 shell 直接执行 python 程序
  - 到用 shell 循环执行 python 程序
- 循环体中
  - 把 python 的输出结果用管道交给了 figlet 程序
  - 把 figlet 输出的结果用管道给了 cowsay
  - 把 cowsay 的结果给了 lolcat
- 最后是提权直接运行程序
- 这一路真的好远啊
	- python3 是脚本解释器
	- shell 也是脚本解释器
	- 其实我们是在 shell 中利用 python3 的输出结果
		- 用 shell 把 python 的粘了起来 
		- 分时输出的 
	- 不过这一路真的好绕
		- 如果能用 python 直接调用 shell 中的命令就好了
		- 那个时候 python 就成了胶水的主体
		- 完成粘合的工作
	- 也许有一天可以做到
- 可以自己做一个小动物来报时吗？

### ascii_art

- 这是一门非常年轻的亚文化

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665540053591)

- 有很多有意思的文本画可以下载

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665540084558)

- 能否将图片转化为asciiart呢？

### 下载 aview 🅰️

- 下载字符画软件包 aview、imagemagick。

```shell
sudo apt update
sudo apt install aview
sudo apt install imagemagick
```

- aview 只接受专门的格式。
- 使用 asciiview 可以转化格式。
- bmp 格式更容易被接受。⚠

```shell
asciiview panda.jpg
```

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/asciiview.png)

- 可以在本机下载之后
- 上传到蓝桥云
- 最好选择png格式
- 成功概率会提高

### 下载图片 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637204997511)

- 注意上传的图片在Code文件夹中
- cd Code可以进入Code文件夹

### 存储字符画

- 通过查询帮助 📕
- 发现字符画可以保存
- 可以把字符画保存为文本、网页等形式
- 在运行
	- asciiview xxx.png之后
	- 出现了字符画面
	- 注意图片中的纯黑部分是以空格来出现的
- 按下快捷键<kbd>s</kbd>
	- 会出现一个菜单
	- 如下图


![Image text](https://labfile.oss.aliyuncs.com/courses/2712/saveImage.png)

- 然后选择Text格式
	- 选 1
	- 后面再设置路径
	- 一路下一步

### 保存过程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665495993965)

- 到这一步选8

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496013025)

- 然后按y
	- 保存
- 然后可以关闭小窗
- ll可以看到文件了
- 字符画的效果需要具体实践验证

### 国画风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151365586)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151346390)

### 表情风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151395424)

### 甲骨文风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151417466)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151429870)

### 大小选择
![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205472280)

- 可以设置分辨率为四分之一大小

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205511652)

### 线稿风格

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496088819)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496102295)

- vi打开这个xxx.txt
	- 鼠标左键选择这段文字
	- 鼠标右键菜单选择复制
- 可以把这个小动物变成cowsay可以用的小动物

### 结合 cowsay🐄

- 先找到位置

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496255713)

- 尝试复制小动物文件

### 复制动物

```shell
# 在确认 cowsay 已经安装的情况下
cd /usr/share/cowsay/cows
# 复制一个 cow 文件
sudo cp apt.cow oeasy.cow
#是用编辑器编辑
sudo vi oeasy.cow ~/Code/ooo.txt
```

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496415681)

### 修改字符画

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496534047)

- 这是原来的字符画
- 把原来的字符画删除
- 粘贴上刚刚复制到剪贴板的自己的小动物字符画
- 然后输出

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/ooo.png)

- 注意可以有一些修改

### 修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496875972)

- 注意
	- 前5行和最后一行
	- 都是有意义的
	- 是cow的结构

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496842742)

### 配合报时

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497615102)

- 使用新动物

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497623840)

### 渐变色

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497647880)

### 配合话语

- 可以再配合一些亚文化的话语

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497879185)

- 做成报时动画😁
- 将我们做的好东西
- 录制成视频
- 发个动态炫一下
- 这就是asciiart!!!
- 如果要说的话比较多
- 就需要角色要变小一点

### 角色大小选择

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205472280)

- 可以设置分辨率为四分之一大小

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205511652)


## 总结

- 这次我们
	- 制作了自己的小动物
	- 还可以让小动物变色、报时
	- 还可以说些话
	- 这很亚文化
	- 很酷炫的亚文化
	- 不是吗？
- 回忆一下我们最最开始研究报时的时候
	- 回到本行行头的方法
    - print("\r"+ascii_time)
    - `\r` 与 `\n` 不同
- 从含义上来看
    - `\n` - LF - LineFeed - 换行
    - `\r` - CR - CarriageReturn - 回车
- 换行和回车具体有什么不同吗？🤔
- 我们下次再说程序！👋
