
# Well

The Basical order:
**git init** //git初始化
**git add .** //把变更加到暂存区
**git commit -m "Initial commit"** //git 提交到本地仓库,后面的是提交的相关信息
**git branch -M main**  // 创建主干
**git remote add origin https://github.com/BassttElSevic/BassttGitPractice.git ** //提交到仓库
**git push -u origin main** //提交

工作区 (Working Directory)
    ↓ git add
暂存区 (Staging Area)
        ↓ git commit
本地仓库 (Local Repository)
            ↓ git push
远程仓库 (Remote Repository - GitHub)

**git init**                          # 1. 初始化本地仓库
**git add .**                         # 2. 添加所有文件到暂存区
**git commit -m "first commit"**      # 3. 第一次提交
**git branch -M main**                # 4. 将主分支命名为 main
**git remote add origin https://github.com/BassttElSevic/BassttGitPractice. git **  # 5. 绑定远程仓库
**git push -u origin main**           # 6. 首次推送（-u 设置上游分支）

这是第一次的

后面我们就可以

**git status**                          # 1. (可选) 查看哪些文件被修改了
**git add .**                           # 2. 添加修改到暂存区
**git commit -m "描述这次提交的内容"**  # 3. 提交更改
**git push**                            # 4. 推送到远程（不需要再加 -u origin main）

什么是 Commit（提交/节点）?

把 Commit 想象成"存档点"
每次你执行 git commit，Git 就会创建一个快照，记录当时所有文件的状态。

时间线 →

        ●───────●───────●───────●
        │       │       │       │
      commit1  commit2  commit3  commit4
     "初始化"  "加了登录" "修了bug" "加了注册"

每个 ● 就是一个 commit 节点，它包含：

�� 当时所有文件的快照
�� 提交信息（commit message）
�� 作者信息
⏰ 时间戳
�� 指向上一个 commit 的指针（父节点）

git log --oneline

# 输出类似：
# a1b2c3d (HEAD -> main) 加了注册功能
# e4f5g6h 修复了登录bug
# i7j8k9l 添加了登录功能
# m0n1o2p 初始化项目

现在你想开发一个新功能，但又不想影响主线代码。这时候就创建一个分支：

git branch feature-login    # 创建新分支
git checkout feature-login  # 切换到新分支

# 或者一步完成：
git checkout -b feature-login

●───────●───────●  (main)
                │
                └── (feature-login) ← 你在这里

在分支上开发
当你在 feature-login 分支上继续 commit：
●───────●───────●  (main)
                 \
                  ●───────●  (feature-login) ← 你在这里
                  │       │
              "登录UI"  "登录逻辑"

想象你在玩一个 RPG 游戏：


主存档 (main)
    │
    ├── 存档点1：完成新手村
    │
    ├── 存档点2：打败第一个Boss
    │
    └── 存档点3：到达王城
           │
           ├─→ 分支A：尝试走魔法师路线
           │
           └─→ 分支B：尝试走战士路线 

如果魔法师路线玩得不好 → 删除分支A，回到主存档
如果战士路线很成功 → 把分支B合并到主存档

main (主分支 - 稳定版本)
  │
  ├── feature-login     (开发登录功能)
  │
  ├── feature-payment   (开发支付功能)
  │
  ├── bugfix-123        (修复bug)
  │
  └── hotfix-urgent     (紧急修复)

 # 确认当前在哪个分支
 git branch

 # 正常开发流程
 git add .
 git commit -m "完成了某功能"

 # 推送分支到远程
 git push -u origin feature-new

 假设 feature-login 开发完成，要合并到 main：

 
# 先切换到 main
git checkout main

# 把 feature-login 合并进来
git merge feature-login

●───────●───────●  (main)
                 \
                  ●───────●  (feature-login)

                  变为

●───────●───────●───────────●  (main)
                 \         /
                  ●───────●  (feature-login)

# 删除本地分支（合并后）
git branch -d feature-login

# 强制删除（未合并也删除）
git branch -D feature-login

# 删除远程分支
git push origin --delete feature-login

HEAD 是什么

HEAD 是一个特殊指针，指向你当前所在的位置。

            ●───●───●  feature-A
           /         \
     ●───●───●───●─────●───●  main
              \           /
                 ●───●───●  feature-B

                图例：
                ● = 一个 commit（提交节点）
                ─ = 提交之间的连接
               / \ = 分支的分叉和合并
                 


 
hahahaha






