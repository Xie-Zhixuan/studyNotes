# 官方文档

<http://git-scm.com/docs>

## 常用

### `git help`

`git help [-a|--all] [-g|--guide]
         [-i|--info|-m|--man|-w|--web] [COMMAND|GUIDE]`

- 不提供参数,则输出git命令的规则和常用git命令
  
- `-a`或`--all`输出所有可用命令
  
- `--guide`或-`g`,列出有用的Git指南。
  
- 给出命令,输出手册. (本职工作)

### `git config`

查看用户的配置信息：
`git config --global --list`

要查看当前仓库的，把global改成local就好, i,e.  
`git config --local --list`

顺带一提,仓库.git目录下的`config`文件保存的就是当前仓库的local配置.而用户的global配置得到用户主目录的`.gitconfig`中.
