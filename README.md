# B站数据看板 - CYBERPUNK 2077 Edition

B站UP主可以通过此面板监控粉丝订阅数量和留言，赛博朋克风格界面。
![效果预览](./效果预览.png)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Style](https://img.shields.io/badge/Style-Cyberpunk-yellow.svg)

## 功能特点

- **实时数据监控** - 粉丝数实时更新（每分钟自动刷新）
- **消息通知** - 显示最新的评论回复和@提及
- **蜂鸣提醒** - 新关注蜂鸣1声，新回复蜂鸣3声
- **字号调节** - 右上角滑块调节字体大小（50%-150%）
- **数据变化追踪** - 从启动开始计算增长，直观显示变化
- **头像显示** - 自动加载B站头像
- **一键跳转** - 点击消息卡片直接跳转到B站回复页面
- **窗口置顶** - 可设置窗口始终置顶显示
- **赛博朋克UI** - 霓虹黄+青蓝+黑色科技风

## 快速开始

### 方式一：直接运行exe（推荐）

1. 从 [Releases](https://github.com/Joohnnwicky/bilibili-up-monitor/releases) 下载 `B站数据看板.exe`
2. 双击运行即可

### 方式二：运行Python源码

```bash
# 安装依赖
pip install pillow requests

# 运行程序
python bilibili_dashboard.py
```

## 设置Cookie（消息功能必需）

消息功能需要B站登录状态的Cookie，请按以下步骤获取：

### 方法一：控制台命令（推荐）

1. 用浏览器（Chrome/Edge）打开 [B站](https://www.bilibili.com) 并**登录**
2. 按键盘 `F12` 打开开发者工具
3. 找到顶部的 **Console**（控制台）标签，点击它
4. 粘贴以下代码，按回车：
   ```javascript
   document.cookie.match(/SESSDATA=([^;]+)/)[1]
   ```
5. 复制输出的结果（不含引号）
6. 点击看板程序的 `KEY` 按钮，粘贴进去保存

### 方法二：手动查找

1. 按 `F12` 打开开发者工具
2. 点击 **Application**（应用程序）标签
3. 左侧展开：Storage → Cookies → `https://www.bilibili.com`
4. 在右侧列表中找到 **SESSDATA**
5. 双击对应的 Value 值，复制
6. 点击看板程序的 `KEY` 按钮，粘贴保存

### 常见问题

| 问题 | 解决方法 |
|------|----------|
| Console在哪里？ | 开发者工具顶部标签：Elements, Console, Network... 中文显示：元素、控制台、网络 |
| 提示 null 或 undefined？ | 说明没有登录B站，请先登录 |
| 复制的内容很长？ | 正常现象，全部复制即可，格式类似：`abc123%2Cdef456%2C789xxx` |
| Cookie有效期多久？ | 一般1-2个月，失效后需要重新获取 |

### 辅助工具

运行 `【第一步】获取B站Cookie.bat` 可打开图文教程窗口，更直观地了解获取步骤。

## 按钮说明

| 按钮 | 功能 |
|------|------|
| SYNC | 刷新数据 |
| MARK | 标记当前数据为基准 |
| TOP | 切换窗口置顶 |
| KEY | 设置Cookie |
| MSG | 刷新消息列表 |

## 自行打包

```bash
pip install pyinstaller
python build_exe.py
```

输出：`dist/B站数据看板.exe`

## 技术栈

- Python 3.8+
- Tkinter - GUI
- Pillow - 图像处理
- Requests - HTTP请求

## 免责声明

本项目仅用于学习和个人使用，请遵守B站相关服务条款。

## 开源协议

MIT License

---

Made with neon lights by 前线观察大队
