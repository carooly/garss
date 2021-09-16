## 一、新手准备

#### 1、开启邮箱的POP3/SMTP服务，
以QQ邮箱为例-->邮箱设置-->账户-->开启服务：POP3/SMTP服务

![](https://github.com/carooly/garss/blob/main/readme/001.PNG)

需要发送短信进行验证

![](https://github.com/carooly/garss/blob/main/readme/002.PNG)

#### 2、获取授权码（即后续配置Settings的PASSWORD）
![](https://github.com/carooly/garss/blob/main/readme/003.PNG)

#### 3、注册github账号（需准备梯子以获得良好体验）
最好还是学习一下git基础知识，廖雪峰的Git教程，https://www.liaoxuefeng.com/wiki/896043488029600

## 二、定制自己的私人简报

#### 1、从 zhaoolee大神的git 仓库（链接：github.com/zhaoolee/garss）, 
fork一份程序到自己的仓库，

![](https://github.com/carooly/garss/blob/main/readme/004.PNG)
然后切换到自己的仓库。
#### 2、在Settings标签中，允许运行actions
![](https://github.com/carooly/garss/blob/main/readme/005.PNG)

同时，去Actions标签检查一下工作流（workflow）--zhaoolee是否已启动，如未启动请手动启动。
![](https://github.com/carooly/garss/blob/main/readme/006.PNG)

#### 3、在Settings中，按照下图设置发件邮箱相关内容。注意：PASSWORD为第一步第2节中获取的授权码！

![](https://cdn.fangyuanxiaozhan.com/assets/1629970189283arACkBKe.png)

#### 4、在根目录, tasks.json中配置收件人。
```
{
    "tasks": [
        {
            "email": "zhaoolee@gmail.com"
        },
    ]
}
```
或者，多个收件人使用数组，
```
{
    "tasks": [
        {
            "email": "zhaoolee@gmail.com"
        },
        {
            "email": "zhaoolee@foxmail.com"
        }
    ]
}
```

#### 5、设置完成后 在README.md文件的底部加个空格，并push（点击最下面的Commit changes按钮），即可触发更新！
每修改一次README.md或者其它文件，提交后（点击Commit changes按钮），均会自动PUSH一次，大概需要运行3分钟，请耐心等等。


## 按照上面的步骤，应该就可以设置成功了，，下面的步骤就可以忽略了！
## 

## 三、如果无法收到邮件，可以按照下面的方法进行测试
### （需要准备梯子）
可以按照以下代码，自测一下自己的HOST, PASSWORD，USER 是否能顺利发邮件
### 注意：PASSWORD即开启POP3/SMTP服务获取的授权码

```
!pip install yagmail

import yagmail

# 连接邮箱服务器
yag = yagmail.SMTP(user="填USER参数", password="填PASSWORD参数", host='填HOST参数')

# 邮箱正文
contents = ['今天是周末,我要学习, 学习使我快乐;', '<a href="https://www.python.org/">python官网的超链接</a>']

# 发送邮件
yag.send('填收件人邮箱', '主题:学习使我快乐', contents)
```

在线自测地址 [Colab： https://colab.research.google.com/](https://colab.research.google.com/)

![在线自测](https://i.v2ex.co/zQWM0V6b.png)

## 发送邮件的效果

![手机端优化后的邮件效果](https://cdn.fangyuanxiaozhan.com/assets/163039979740967wCT8RQ.jpeg)

![PC端优化后的邮件效果](https://cdn.fangyuanxiaozhan.com/assets/1630399693988c2tk8n7k.png)

