# wxautoapi

微信版本：3.7.0.29

更新日期：2022.07.08

版本：测试版，请勿转卖

## 开始使用

**<font color='red'>注意：该项目只支持Windows PC微信3.7.0.29版本，调用前请先检查版本！！！</font>**

**<font color='red'>注意：该项目只支持Windows PC微信3.7.0.29版本，调用前请先检查版本！！！</font>**

**<font color='red'>注意：该项目只支持Windows PC微信3.7.0.29版本，调用前请先检查版本！！！</font>**

![WeChatVersion](https://github.com/cluic/wxautoapi/blob/main/Images/%E5%BE%AE%E4%BF%A1%E7%89%88%E6%9C%AC.png)


## 快速开始：

### 1. 调用实例

```python
>>> from wxautoapi import WeChat

# 登录微信（已登录的微信请先退出）
>>> wx = WeChat()
成功启动微信：1804，等待登录...
微信已登录 (<wxid_xxxxxxxxxxxxx>, XXXX)>>>>>>>

# ======================= 注意！ =======================

# 请确保微信已登录后，再运行下述步骤，否则无法正常调用相关方法！！！
# 请确保微信已登录后，再运行下述步骤，否则无法正常调用相关方法！！！
# 请确保微信已登录后，再运行下述步骤，否则无法正常调用相关方法！！！

# ======================= 注意！ =======================

# 文件传输助手
>>> wx.filehelper.send_text('你好！')
>>> wx.filehelper.send_file('D:/test.txt')

# 查找好友
# 方法一（不知道wxid）：查找备注为张三的好友
>>> person = wx.find_person(by='remark', value='张三')
>>> person.send_text('你好~')
# 方法二（知道wxid）：
>>> person = wx['wxid_xxxxxxxx']

# 查找群（查找备注为工作1群的微信群）
>>> group = wx.find_group(by='remark', value='工作1群')
>>> group.send_text('大家好')

# 获取消息
>>> Messages = wx.getmsgs()
>>> Messages  # 返回一个消息列表，包含所有消息对象
[<WeChat TextMessage Element at 0x2a2781e16a0>,
 <WeChat ImageMessage Element at 0x2a276d7dc18>,
 <WeChat Other Message Element at 0x2a276d7dba8>,
 <WeChat TextMessage Element at 0x2a276d7dc50>,
 <WeChat TextMessage Element at 0x2a276d7d908>]
>>> msg = Messages[0]
>>> msg.text # 消息内容
"xxxxx"
```

### 2. 多开实例

```python
>>> from wxautoapi import WeChat

>>> n = 3  # 多开数量，例如同时开启3个微信
>>> wxdict = {f'wx{i}':WeChat() for i in range(n)}  # 
>>> wxdict
{'wx0': <WeChat Object at 0x2a275e15f28 - (未登录)>,
 'wx1': <WeChat Object at 0x2a276804320 - (未登录)>,
 'wx2': <WeChat Object at 0x2a27681cbe0 - (未登录)>}
# 登录微信之后，所有操作与调用实例一样
>>> wxdict['wx0'].filehelper.send_text('123') # 操作第一个微信向文件传输助手发送消息：123
```

![MultiApp](https://github.com/cluic/wxautoapi/blob/main/Images/%E5%A4%9A%E5%BC%80%E7%A4%BA%E4%BE%8B.png)



## 声明

**<font color='red'>1. 本项目仅供学习研究，不可用于违法犯罪活动，因本项目造成的任何后果与作者无关</font>**

**<font color='red'>2. 本项目完全独立，跟作者无任何信息交互，不存在任何盗取数据的行为，如若发现可报警处理</font>**
