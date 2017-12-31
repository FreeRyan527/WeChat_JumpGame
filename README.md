# 用Python来玩微信跳一跳,个人心得


[原github项目地址](https://github.com/wangshub/wechat_jump_game)

本项目引自上面的链接，我只是根据自己的手机调整了一些参数，以及一些自己在配置过程遇到的坑和大家讨论

## 配置环境
	* Mac OS
	* IPhone 6s plus



## 配置步骤

1.使用真机调试wda，参考iOS 真机如何安装 [WebDriverAgent · TesterHome](https://testerhome.com/topics/7220)

* 文章中有提到需要签名证书，本人亲测不需要去买，可以直接把自己的apple id申请为开发者账号（请百度搜索Apple Developer），然后就会有免费证书可以使用了。
* 关于文章中脚本安装那一块，原文中：

```
	$ brew install imobiledevice
```
```
	$ iproxy 8100 8100
```

应更改为

```
	$ brew install limobiledevice 
```
```
	$ iproxy 8100 8100
```


2.安装[openatx/facebook-wda](https://github.com/openatx/facebook-wda)

3.Python 3

* 建议使用homebrew安装

``` shell
	brew install python3
```

## 依赖安装

``` bash
    pip install -r requirements.txt
```

* 因为上述安装方法会因网络原因失败很多次（本人失败了一晚上，汗。。。）此处建议使用wda给的推荐安装
``` bash
    pip3 install --pre facebook-wda
``` 
* 我也少做修改了，装在python3的Frame里，不然后面运行python3文件的时候会报错

## IOS手机操作步骤

1. 运行安装好的 `WebDriverAgentRunner`
2. 将手机点击到《跳一跳》小程序界面
3. `python3 wechat_jump_iOS_py3.py`
4. 依次点击起始位置和目标位置，实现蓄力一跳
5. 打开 `python3 wechat_jump_iOS_py3.py`，根据蓄力一跳的精准情况更改其中的 `time_coefficient`，直到获得最佳取值

> 事实证明，机器人比人更会玩儿游戏。

## 其他说明

由于本人是github小白，不知道这里面可以留言不可以，欢迎去我的CSDN博客留言，那篇文章仅做留言用具体内容都在这里
[CSDN博客留言版](http://blog.csdn.net/ryan_92/article/details/78943805)
