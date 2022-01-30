# 添加子模块
    git submodule add <repo> [path]
影响：
1. 主仓库生成*.gitmodules*文件，里面包含引用的子模块仓库URL。
2. *.git/config*文件包含引用的子模块仓库URL。
3. *.git/modules*包含子模块仓库的*objects*。
4. 会在执行git submodule add的当前目录按照***[path/]repo***的规则创建子模块仓库的克隆。（注：如果你是新克隆的主仓库，子模块仓库不会跟着克隆，需要自主执行`git submodule init && git submodule update` or `git submodule update --init --recursive`）。

# 删除子模块

    git submodule deinit [path/]<repo>
    git rm -rf --cached [path/]<repo>
    手动删除.gitmodules中关于子模块的引用，并且手动删除.git/modules子模块的objects。

影响：
1. *.git/config*中的引用去除
2. ***[path/]repo***目录变空
