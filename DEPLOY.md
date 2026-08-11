# 部署到 GitHub Pages 指南

## 🎯 目标
把这个简历变成一个永久网址,比如:
`https://642995562.github.io/viola-resume/`

## 步骤 1:在 GitHub 上创建空仓库

1. 打开 https://github.com/new
2. 登录你的账号(642995562@qq.com)
3. 填写:
   - **Repository name**: `viola-resume`(必须这个名,Pages 才能用 `用户名.github.io/viola-resume/` 这种路径)
   - **Description**: 中提琴演奏简历
   - **Public**(必须选 Public,免费 Pages 只对 Public 仓库开放)
   - **不要勾选** "Add a README file"、".gitignore" 等任何选项(我本地已经准备好了)
4. 点 **Create repository**

创建完你会看到一个页面写着 "…or push an existing repository from the command line",
**先放着别关**。

## 步骤 2:把代码推上去(3 行命令)

回到终端,我会帮你跑前 2 行,**第 3 行 `git push` 需要你来**,因为需要你的 GitHub 认证。

我会执行:
```bash
cd viola-resume
git add .
git commit -m "Initial commit: 中提琴演奏简历"
```

**然后你来执行这一步**(粘贴到终端回车):
```bash
git remote add origin https://github.com/642995562/viola-resume.git
git branch -M main
git push -u origin main
```

push 的时候,会弹窗让你输入 GitHub 用户名和密码。
**⚠️ 这里输入的不是你 QQ 邮箱的密码!**

> GitHub 已经不再支持用账号密码 push 了,改用 **Personal Access Token (PAT)**。
> 没有 PAT 的话先去这里生成一个:https://github.com/settings/tokens/new
> - Note 随便填,比如 "viola-resume-push"
> - Expiration 选 90 days 或更长
> - 勾选 **`repo`** 整个 scope
> - 点 Generate token
> - **复制那个 token**(只显示一次!)
> - 把它当密码粘贴到 push 的提示框里

## 步骤 3:启用 GitHub Pages

1. 回到刚才那个 GitHub 仓库页面
2. 点顶部的 **Settings**
3. 左侧菜单找 **Pages**
4. **Source** 选 **Deploy from a branch**
5. **Branch** 选 `main` / `/ (root)`
6. 点 **Save**
7. 等 1-2 分钟,刷新页面,会显示一行绿色的网址:
   > 🎉 Your site is live at `https://642995562.github.io/viola-resume/`

把这个网址发给任何人,他们都能看到你的简历 ✨

## 以后怎么更新内容

我帮你改完简历后,你来执行:

```bash
cd viola-resume
git add .
git commit -m "更新内容"
git push
```

GitHub Pages 会自动重新部署,等几十秒到 1 分钟就能看到新版本。

---

## 🔐 安全建议

- **不要再把密码告诉任何 AI / 任何人**(包括我)
- 启用 GitHub 的 **2FA**(两步验证):https://github.com/settings/security
- 上面生成的 PAT 只用于 push,不要分享、不要写进代码
