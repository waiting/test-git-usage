# 添加子模块并且重命名子模块的文件夹名

## 方式一：

    git submodule add [-name <new_name>] <repo> [path]

***new_name*** 表示子模块新的名字（此将代指你的新名字，并用 ***斜黑体*** 重点突出）， repo 表示仓库URL， path 表示子路径。

遗憾的是执行上面命令后，并未完成任务要求，还需要手动更改文件夹名和修改一些文件：
1. 修改克隆的模块文件夹名为 ***new_name*** 。
2. 修改 *.gitmodules* 文件中 ***new_name*** 子模块仓库的`path`为你新文件夹的名字 ***new_name*** 。
3. 修改 *.git/modules/***new_name***/config* 文件中`worktree`的相对路径。


## 方式二（未验证）：
普通的添加子模块后执行：

    git mv <submodule_oldname> <new_name>
    git submodule sync


添加子模块的详细可以查看[Add git submodule](add-submodule.md)。

