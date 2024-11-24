# 本人配置
机型 ：macbook pro 16+512 m1pro

硬盘 ： 放本地硬盘不够用了，我是放在外置硬盘里的，用的是闪迪-E61-1TB固态

系统 ： macOS Sequoia 15.1

unreal版本 ： 5.4.4 

> [!WARNING]   
<font color="#DF2A3F">1. ue5.5似乎有问题，不一定能编译成功。</font>  
<font color="#DF2A3F">2. 下面步骤中运行两个command文件的时候，如果你也是最终打算在外置固态里编译，下载依赖和生产项目文件前就要扔到固态里然后在硬盘里打开这两个command，不可以本地弄好了后再拖进去！！！ 本地编译请忽略。</font>  
<font color="#DF2A3F">3. 请使用最新版本xcode，本人版本16.1，xcode和macOS版本有一定关系，必要时请升级macOS版本，app store下载xcode即可。我第一次编译就是因为xcode版本不对导致My Mac旁边没有list来编译QAQ</font>  
<font color="#DF2A3F">4. 硬盘格式化为APFS（Apple 文件系统），exFAT未尝试，可能存在影响，也可能不存在</font>  

![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732242770175-1a69e6c3-4751-4a87-bf4b-6d48f5689f78.png)

<font color="#DF2A3F">（官方教程也有温馨提示，升级最新版Xcode）</font>

# 步骤
大致和官方github中的read me是相同的，补充一点细节

## 1.下载
在releases页面下载具体版本，git下载不太稳定，我直接下的zip

![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732242699403-aca97786-d96d-4b14-af62-85abd87af16b.png)

## 2.Setup.command
这里主要是安装一些依赖。

没什么好说的，右键然后点击open。如果不让运行（apple无法识别该开发者什么什么不安全），可以去设置-隐私与安全性拉到最下面，允许该程序运行即可。

**<font color="#DF2A3F">Warning :</font>**

> [!WARNING]  
如果出现依赖装到99%就不动了，大概率是你文件路径太长了，我也遇到了，所以我直接放根目录下面了。可以去网上再搜搜具体解决方案，大概率就是这个问题。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732243031437-ba761261-b02d-4e90-ae53-4b07dc05ab38.png)

## 3.GenerateProjectFiles.command
点开同一文件夹的 GenerateProjectFiles.command，生成xcode项目文件，不出意外，几分钟就好了。

## ![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732243146514-d160f920-bc3b-4f3b-80bd-30472a1a7956.png)
然后点开xworkspace项目文件![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732243239899-5ac759ad-6f22-4e28-b530-d7ab17631b1f.png)

下面就正式进入编译了

## 4.编译着色器
My Mac 旁边选择Shader CompileWorker，然后上方菜单栏Product -> build，这步挺快的，大概也就个几分钟

![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732243896002-1fed4e3b-b31c-432f-9e15-2a03af49f2a4.png)![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732243936461-e189f44e-ced3-4d07-a0ed-424aaf7b8ce7.png)



## 5.编译editor
My Mac 旁边选择Unreal Editor，然后上方菜单栏Product -> build，这里比较慢了，我的电脑大概编译了2小时，可以找点别的什么事情干干，然后2小时后回来看一眼。编译完Product -> run，就可以看到editor界面了。

后续可以在Engine/Binaries/Mac 下面找到Unreal Editior这个应用程序，直接双击就可以打开了。



![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732244169366-277d5d22-e0de-46c5-8e84-cd15b23fe9de.png)



## 6.创建项目
找个文件夹来存项目，创建完后会默认会打开一个xcode工程，这里官方文档没有提。

这个项目中要选择 xxx（你的项目名，我这里是HELLOMOON）Editor，然后直接product - run 即可。应该也要个4-5分钟，然后就能看到界面了～

![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732244287859-14c50bda-1612-4bfe-bb6f-5d07a68811f6.png)![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732244375635-e08f7488-8008-4317-bc9c-2ec1ad067dc6.png)

## 成功截图！
![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732244618182-52792c20-15d8-4c51-925b-75b9a80289ff.png)

## 打包mac平台成功
![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732251606981-7811e205-1b10-4446-88e8-fc0615c2d275.png)![](https://cdn.nlark.com/yuque/0/2024/png/42546699/1732251781764-764c5068-87e8-46c3-ab58-6c4736f7065e.png)

