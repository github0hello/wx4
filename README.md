# 微信自动化工具

这是一个基于Python的微信桌面客户端自动化工具，使用uiautomation库实现对微信4.x界面的控制，可以帮助用户自动化执行微信的各种操作。

## 项目介绍

该工具通过UI自动化技术控制微信桌面客户端4.x，实现以下功能：

- 自动发送文本消息
- 获取聊天记录

该工具适用于需要自动化处理微信消息、批量操作或监控微信的场景，如自动客服、消息监控、自动回复等。

## 安装指南

### 前提条件

- Python 3.12+
- 微信桌面客户端4.x版本
- Windows操作系统

### 安装步骤

1. 克隆或下载本项目到本地

2. 安装所需依赖
```bash
pip install uiautomation pyperclip pyautogui pillow loguru
```

3. 确保微信桌面客户端已安装并能正常登录

4. 创建日志目录（可选）
```bash
mkdir logs
```

## 使用示例

### 初始化微信控制

```python
from wx4 import WeChat

# 创建微信控制实例
wx = WeChat()
```

### 发送消息

```python
# 发送消息到当前聊天窗口
wx.SendMsg("你好，这是一条自动发送的消息")
```

### 获取消息

```python
# 获取当前聊天窗口的所有消息
messages = wx.GetAllMessage()
for msg in messages:
    print(f"发送者: {msg.sender}, 内容: {msg.content}")
```

### 主要类

- `WeChat`: 微信控制的主类，提供各种微信操作的方法
- `MSG`: 表示一条微信消息，包含发送者、内容和索引信息


### 注意事项

- 使用前请确保微信已登录
- 部分功能可能受微信版本更新影响
- 使用自动化工具时请遵守微信的使用条款,如果出现任何问题与作者无关