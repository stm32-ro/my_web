# Day 4 问答笔记（Git 与 GitHub：代码上云）

## 一、GitHub 是什么

- 程序员的"云端档案馆"：存放代码和笔记，永不丢失
- 账号名：**stm32-ro**
- 我的仓库：https://github.com/stm32-ro/my_web（Public 公开）

### 核心概念（一句话版）
- **仓库（repository）**= 一个项目的云端文件夹
- **commit（提交）**= 给项目拍一张"快照"，附带说明
- **push（推送）**= 把快照上传到云端
- **clone（克隆）**= 从云端把项目下载到电脑

## 二、注册与建仓库

- 右上角 `+` 号 → **New repository**
- Repository name：`my_web`，选 **Public**
- ❗其他全部**不勾**，保持空仓库

## 三、安装 Git

- 验证：`git --version` → 我的版本 **2.33.1**
- 首次使用"报户口"（只需一次）：

```powershell
git config --global user.name "stm32-ro"
git config --global user.email "13719612170@163.com"
```

- 作用：告诉 GitHub"这些提交是谁干的"
- 执行后没有输出 = 成功（老规律）

## 四、今天踩的坑 ⭐

### 坑 1：`unknown switch 'r'` 报错（两次！）
- 原因：网址 `stm32-ro` 中间混进了一个**空格**，Git 把 `-r` 当成了命令选项
- **解决：网址永远从浏览器地址栏复制，永远不要手打**

### 坑 2：仓库页面还显示 Quick setup 引导页
- 原因：浏览器停在旧页面（缓存）
- 解决：按 **F5 刷新**

## 五、第一次 push 全流程

```powershell
git init                  # 初始化本地仓库（每个项目只做一次）
git remote add origin https://github.com/stm32-ro/my_web.git   # 绑定云端（只做一次）
git add .                 # 把所有改动放进"待提交区"
git commit -m "Day 4：第一次提交，上传学习笔记"   # 拍快照
git branch -M main        # 分支命名为 main（只做一次）
git push -u origin main   # 上传云端（第一次要 -u，以后不用）
```

### 授权弹窗流程（第一次 push 时）
1. 弹窗 → 点 **Sign in with your browser**
2. 浏览器授权页 → 点绿色 **Authorize git-ecosystem**
3. 显示 **Authentication Succeeded** → 回 VS Code
4. 终端出现 `* [new branch] main -> main` = 成功
5. 凭证已记住，**以后 push 不再弹窗**

## 六、成功的标志

- 终端：`5 files changed, 128 insertions(+)`（5 个文件 128 行上云）
- 终端：`[main (root-commit) 7d5d79e]`（提交的"身份证号"）
- 网页：文件列表出现，**Markdown 自动渲染成漂亮排版**

## 七、日常三连（以后的每日习惯，背下来！）

```powershell
git add .
git commit -m "Day X：随便写什么说明"
git push
```

## 八、看懂 Git 输出的关键英文

| 英文 | 意思 |
|---|---|
| `unknown switch 'r'` | git 不认识 `-r` 选项 → 命令里混了空格/打错了 |
| `Everything up-to-date` | 云端已经是最新的 |
| `new branch main -> main` | 上传完成 |
| `root-commit` | 第一次提交 |
| `N files changed` | 这次提交改了几个文件 |

## 九、今日成果
- [x] 注册 GitHub 账号 stm32-ro
- [x] 创建仓库 my_web
- [x] 安装 Git 2.33.1 并完成报户口
- [x] 排查 unknown switch 'r'（空格坑）
- [x] 人生第一次 push 成功 🎉
- [x] 云端仓库验证成功

## 十、明天预告
- Day 5：第一周总复习 + 阶段小测验
- Day 6：正式开始写网页（HTML）！