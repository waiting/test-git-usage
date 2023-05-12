# 已提交的文件假定不再更改
实际开发中一些文件需要提交到仓库里，但是后面的更改又不需要追踪。

    git update-index --assume-unchanged FILE

`FILE`只能是文件或者文件通配符

# 恢复追踪

    git update-index --no-assume-unchanged FILE

# 恢复全部
    git update-index --no-assume-unchanged `git ls-files -v | grep -e "^[hsmrck]" | sed 's/^..//'`

`FILE`同上

# 查看当前被忽略的已提交的文件

    git ls-files -v | grep -e "^[hsmrck]" | sed 's/^..//'

