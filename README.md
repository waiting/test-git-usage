# test-git-usage
This repository is used to test the usage of git.

# 添加子模块
    git submodule add <repo> [path]
影响：
1. 主仓库生成.gitmodules文件，里面包含引用的子模块仓库URL。
2. .git/config文件包含引用的子模块仓库URL。
3. .git/modules包含子模块仓库的git objects。
4. 会在执行git submodule add的当前目录按照[path/]repo_name的规则创建子模块仓库的clone（注：如果你是clone主仓库，子模块仓库不会跟着clone，需要自主执行git submodule init、git submodule update）。

# 删除子模块
    git submodule deinit [path/]<repo>
    git rm -rf --cached [path/]<repo>
影响：
1. .git/config中的引用去除
2. [path/]repo_name目录变空
3. 其余不变，需要手动删除.gitmodules中关于子模块的引用，并且手动删除.git/modules子模块的objects。
