# branch-pruner-action v1.0
## 这是什么：
1.有的时候，你不小心`Push`了一些敏感数据，你希望清除历史提交记录以抹除这些数据，但你又无法回滚或者不希望因此重建这个仓库...

2.随着你对仓库的不断`Push`，历史提交记录将会不断堆积，仓库的体积也随之上升。有的时候不断增大的体积可能会对你造成困扰，而你只是个人项目，并不需要保留这些提交记录...

**「此项目可以帮助你对你的仓库历史提交记录进行修剪，通过变基剪枝的方式来删除你所不需要的部分历史提交记录，以此减小仓库体积或删除敏感数据」**

## 注意事项：
1.如果你的项目大于2G请使用 [ [v2.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v2) ] 版本——此项目无法作用在排除历史提交后，仓库文件总体积仍然大于2G的分支上，若大于2G，脚本会报错并安全退出终止执行，不会破坏仓库现有状态（这是由于单次`Push`的缓冲区限制原因，最大为2G，无论你用`ssh`还是`http`，单次`Push`都不能大于2G，`Push`不上去自然就不会产生任何修改）。

2.此版本是所有版本中唯一能够选择性保留现有分支内容的版本，但是注意——执行此项目后，所有保留下来的历史提交记录都将获得新的`Commit Name`、`Commit Email`、`Massage`、`Hash`、`Time`...

[ 下图为该示例分支选择不保留任何历史记录时，执行脚本后的历史提交记录状态 ]
![image](https://github.com/Container-Zero/Branch-Pruner-Action/assets/20435019/b63364f2-7d68-4d1d-b32f-fdd24ae78a3f)

## 使用方法：
1.**为了防止意外情况，请在操作前备份你的仓库，或新建一个临时仓库进行脚本实验，确保功能符合你的需求。**

2.首先需要赋予`Github Action`权限——前往要清理历史记录的仓库，依次点击 `Settings`-`Actions`-`General` 找到 `Workflow permissions` 中的 `Allow GitHub Actions to create and approve pull requests` 与 `Read and write permissions` 选项，将其勾选并保存。

3.拉取该分支内的`branch_pruner_v1.0.yml`文件，并在`Github Action`中保存，保持命名为`branch_pruner_v1.0.yml`并执行此Action。


