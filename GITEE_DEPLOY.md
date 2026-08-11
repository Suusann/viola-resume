# 部署到 Gitee Pages 指南(国内访问)

## 🎯 目标
让国内访问也快速稳定:
`https://suusann.gitee.io/viola-resume/`

(对比 GitHub Pages 国内访问慢,这个版本国内打开 1-3 秒)

## 步骤 1:注册 + 实名 Gitee

1. 打开 https://gitee.com 注册账号(用户名最好用 `Suusann`,保持一致)
2. 注册后立刻做**实名认证**:
   - 右上角头像 → 设置 → 实名认证
   - 上传身份证正反面 + 人脸识别
   - 通常 5-10 分钟通过
3. ⚠️ 没实名认证无法启用 Pages

## 步骤 2:创建仓库

打开 https://gitee.com/projects/new

| 字段 | 填什么 |
|---|---|
| **仓库名称** | `viola-resume`(必须和 GitHub 那个完全一致) |
| **路径** | 自动填充 `Suusann/viola-resume` |
| **仓库介绍** | 中提琴演奏简历 |
| **是否开源** | **公开**(Pages 必须公开) |
| **使用 Readme 文件初始化仓库** | **不勾选**(本地已有) |
| **选择语言** | 不重要 |

点 **创建**

## 步骤 3:推送代码

回到终端(我已经把 gitee remote 加好了,直接 push 即可):

```bash
cd /Users/zhengyanjia/.minimax-agent-cn/projects/viola-resume
git push -u gitee main
```

按提示输入:
- **Username**: `Suusann`(你的 Gitee 用户名)
- **Password**: 你的 Gitee 密码(Gitee 支持密码 push,不用 PAT)

## 步骤 4:启用 Gitee Pages

1. 进入 Gitee 仓库主页 https://gitee.com/Suusann/viola-resume
2. 顶部菜单点 **服务** → **Gitee Pages**
3. 第一次会弹一个**实名认证 + 仓库公开**的检查页
4. 选择 **master** 或 **main** 分支(看哪个有内容)
5. 部署目录:**/(root)**
6. 点 **启动**
7. ⚠️ 首次部署会进入**审核队列**,通常 **1-2 个工作日**通过
8. 审核通过后会显示你的网址:
   > ✅ `https://suusann.gitee.io/viola-resume/`

## 以后怎么更新

我帮你改完简历后,你来执行(同时推两个平台):

```bash
cd /Users/zhengyanjia/.minimax-agent-cn/projects/viola-resume
git add .
git commit -m "更新内容"
git push          # 推 GitHub
git push gitee    # 推 Gitee
```

两个网站会同时更新 ✨

---

## ⚠️ 注意事项

1. **实名认证 = 上传身份证**
   - Gitee 是阿里旗下的代码托管平台,数据在国内
   - 身份证信息是必要的实名要求,平台承诺不外泄
   - 如果你**极度在意隐私**,可以只用 GitHub Pages,或者用 Vercel(免认证)

2. **免费版 Gitee Pages 限制**
   - 仓库必须公开
   - 仓库大小 ≤ 500MB(我们这个 1.7MB 远低于限制)
   - 每月访问次数有限(但个人简历完全够用)
   - 升级 Gitee Go(付费)可解锁更多

3. **Gitee Pages 审核被拒常见原因**
   - 实名认证未完成 → 完成认证即可
   - 仓库是私有 → 改成公开
   - 内容违规 → 我们这个纯个人简历不会有这个问题
