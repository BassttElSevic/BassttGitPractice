
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

