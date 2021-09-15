## 一、新手准备
#1、最好准备好梯子
#2、开启邮箱的POP3/SMTP服务，

获取授权码（即github后续配置的PASSWORD）


## 二、定制自己的私人简报

#1、从 zhaoolee大神的git 仓库（链接：github.com/zhaoolee/garss）, 
fork一份程序到自己的仓库，然后切换到自己的仓库。

#2、在settings标签中，允许运行actions
![允许运行actions](https://cdn.fangyuanxiaozhan.com/assets/1630216112533FANcC1QY.jpeg)

同时，去actions标签检查一下zhaoolee的工作流（workflow）是否已启动，如未启动请手动启动。


#3、在settings中，按照下图设置发件邮箱相关内容。注意：PASSWORD为第一步第2节中获取的授权码！

![](https://cdn.fangyuanxiaozhan.com/assets/1629970189283arACkBKe.png)

#4、在根目录, tasks.json中配置收件人。
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

#5、设置完成后 在README.md文件的底部加个空格，并push（点击最下面的Commit changes按钮），即可触发更新！


## 三、无法收到邮件怎么办（需要准备梯子）

可以按照以下代码，自测一下自己的HOST, PASSWORD，USER 是否能顺利发邮件

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

