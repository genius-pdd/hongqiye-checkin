# 红旗云·每日自动签到

基于 GitHub Actions 的每日自动签到，无需开电脑、无需开浏览器。

## 使用方法

### 1. 创建一个 GitHub 仓库

在 [github.com](https://github.com) 创建一个新的仓库（任意名称，公开/私有均可）

### 2. 推送代码

```bash
# 在你电脑上执行
cd C:\Users\23602\hongqiye-checkin
git init
git add .
git commit -m "添加每日自动签到"
git remote add origin https://github.com/你的用户名/你的仓库名.git
git push -u origin main
```

### 3. 设置仓库 Secrets

在 GitHub 仓库页面：
- **Settings → Secrets and variables → Actions → New repository secret**

添加以下 3 个 Secret：

| Secret 名称 | 值 |
|------------|-----|
| `BASE_URL` | `https://cloud.hongqiye.com` |
| `ACCESS_TOKEN` | `O5/Q6vRegREXZuBfE7SBP92P8fPPfu0=` |
| `USER_ID` | `12038` |

### 4. 启动

- 每次推送会自动触发
- 也可以手动触发：**Actions → 每日自动签到 → Run workflow**
- **每天 UTC 00:30（北京时间 08:30）自动签到**

---

## 重要提醒

- Access Token 如果过期了，需要重新从网站获取并更新 Secret
- 签到失败会在 GitHub Actions 日志中显示，可以设置邮件通知

## Token 过期怎么办？

1. 打开 https://cloud.hongqiye.com/console/personal → 安全设置 → 系统访问令牌
2. 重新生成 Token
3. 去 GitHub 仓库 Settings → Secrets 更新 `ACCESS_TOKEN`
