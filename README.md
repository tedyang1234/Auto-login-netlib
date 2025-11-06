## Netlib 保活脚本
这是一个用于自动登录 Netlib 网站以保持账户活跃的 Node.js 脚本，配合 GitHub Actions 实现定时执行。

### 功能特点
🔐 自动登录 Netlib 账户(单账户或多账户)
👥 支持多账户批量处理
⏰ 每60天自动执行一次
📱 执行结果通过 Telegram 通知
🇭🇰 使用香港时区显示时间

### 环境变量配置
1. 在 GitHub 仓库的 Settings → Secrets and variables → Actions 中添加以下环境变量
```
ACCOUNTS	Netlib账户信息(必填)，格式：user1:pass1,user2:pass2

BOT_TOKEN	 Telegram机器人Token	123456:ABC-DEF1234ghIkl-zyx57W2v1u1212Dtr
CHAT_ID	   Telegram 聊天ID	  123456789
不需要telegram通知可不配置
```

使用方法
2. GitHub Actions 自动运行
脚本会自动每60天执行一次

1. 本地运行
bash
# 安装依赖
npm install

#### 安装 Playwright 浏览器
npx playwright install chromium

#### 设置环境变量并运行
ACCOUNTS="user1,pass1;user2,pass2" \
BOT_TOKEN="your_token" \
CHAT_ID="your_chat_id" \
npm start

### 注意事项
1. 确保 Netlib 账户密码正确
2. 首次运行 GitHub Actions 需要授权
3. 脚本执行时间为 UTC 0:00（香港时间 8:00）
4. 如果不需要 Telegram 通知，可不配置相关环境变量


### 许可证
GPL 3.0
