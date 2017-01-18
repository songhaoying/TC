## 前言

- 这个小软件的开发初衷是，最近在用Markdown记笔记发现要弄图片上去很麻烦，一般的步骤至少都是截图-->保存-->选择图片-->上传-->获取外链，现在可能有一些软件可以直接粘贴，但我还没找到，又懒得找，加上又希望自己能管理这些图片而不是上传到公共图床，所以就想自己写一个，本来是想学点Python写的但是写到一半发现很多不熟悉的东西相关的操作方法也没找到就放弃了，就想说一直在练Android还没写过Java的电脑端程序就想试试，于是就有了现在这个TC小工具。

## 关于主角TC

- 运行环境  
	需要在安装有JDK(7.0及以上)的电脑，目前我自己只有Windows电脑，所以不知道其他平台的能不能用（Java是跨平台。。。？！）  

- 功能
	![](http://ojrfmxxyi.bkt.clouddn.com/2017%E5%B9%B401%E6%9C%8817%E6%97%A517_13_09_288.png)
	1.剪切板监听  
		开启剪贴板监听后，当检测到剪切板有新的截图时（系统截图功能或者QQ截图）就会将图片上传到指定的七牛云，并将外链复制到剪切板，粘贴即可，外链已经处理成Markdown的图片格式即` ![](http://ojrfmxxyi.bkt.clouddn.com/2017%E5%B9%B401%E6%9C%8817%E6%97%A517_13_09_288.png) `这种格式，关闭后将不会进行监听和自动上传，所有的数据均只会上传到您设定的七牛云不会和有任何窃取信息行为
	2.上传剪切板图片
		这是在自己不希望截图的时候直接上传设置的，当使用QQ或者系统自带的截图软件进行截图后，点击此按钮即可手动上传
	3.将本地图片拖进窗口上传
		本来想实现的是当复制的文件是图片时进行上传，但是没找到比较好的方法，使用循环来进行检测又怕占用资源，所以就使用了折中的方案，直接将图片拖进窗口，并且此功能的一个有点是可以进行批量上传，可以将多张图片拖进窗口进行上传，软件将会将这些图片的链接整合在一起复制到剪切板
	4.其他
		TC首次运行并链接七牛云时会在所在的路径下创建一个Config文件夹，并在文件夹中创建一个保存信息的文件，以便后面开启软件时直接读取记录，节省反复输入信息的麻烦，可通过软件中的删除配置功能或者手动删除该文件夹或文件即可输入新的信息。使用剪切板上传图片时会先在程序所在目录生成一个图片，上传后会删除，不要再上传过程删除掉。安装完JDK并且配置好环境变量，后重启电脑，启动后双击即可打开该程序。

- 注意事项  
	我现在只试过QQ和Windows自带的截图功能，其他的截图软件和功能没试过，如果原理都是将图片暂时存储在剪切板则都可以使用，本软件也只在Windows8.1上进行测试通过，没有在其他平台和环境中进行测试，请须知

- 运行的视频地址
  [https://v.youku.com/v_show/id_XMjQ3NTYyNDc5Mg==.html?spm=a2h0w.8278793.2736843.4](https://v.youku.com/v_show/id_XMjQ3NTYyNDc5Mg==.html?spm=a2h0w.8278793.2736843.4 "https://v.youku.com/v_show/id_XMjQ3NTYyNDc5Mg==.html?spm=a2h0w.8278793.2736843.4")

## 关于设置七牛云

- 程序的主界面是这样的
   ![](http://i.imgur.com/SVBPGSe.png)
	由于没有找到七牛云连接时是否会返回错误信息，所以连接时并不会提示是否连接成功，会直接进入功能界面，这点有些坑爹，如果有哪位童鞋知道怎么获取连接是否成功的方式请分享下谢谢（现在设想的是先上传一个小测试图片看能否上传成功来判断是否连接成功）  

	1.Access Key And Secret Key：  
	在七牛云的个人中心-->密匙管理中可以找到
	![](http://ojrfmxxyi.bkt.clouddn.com/2017年01月18日14_14_32_570.png)
	
	2.BucketName:  
	进入七牛-->对象存储中，BucketName即你要上传的图片的存储空间的空间名，创建的空间一个要为公开空间  
	![](http://ojrfmxxyi.bkt.clouddn.com/2017年01月18日14_18_49_081.png)
	3.Domain:
	Domain是每个存储空间都有的域名
	![](http://ojrfmxxyi.bkt.clouddn.com/2017年01月18日14_20_30_496.png)
	即图中的默认外链域名

## 结语

**因为是第一次写Java电脑端程序，加上自己的Java水平太低，代码很一般，就先不放源码出来了，等感觉可以一点了，会将源码上传，还请见谅**。非常感谢您看到这最后面，这就是对我最好的鼓励，smileorigin只是一个初级的小开发者，如本程序有什么问题，本人会积极解决，我将此小工具发出来也只是个尝试，抱着很多用Markdown写博客的人或许会需要的的小期望尝试下，非常感谢您看完这篇介绍文章。  
<h3 align = "right">-- smileorigin<h3>  
<h3 align = "right">2017/1/18 15:00:32 <h3>  