# branch-pruner-action v3.0
## 这是什么：
1.有的时候，你不小心`Push`了一些敏感数据，你希望清除历史提交记录以抹除这些数据，但你又无法回滚或者不希望因此重建这个仓库...

2.随着你对仓库的不断`Push`，历史提交记录将会不断堆积，仓库的体积也随之上升。有的时候不断增大的体积可能会对你造成困扰，而你只是个人项目，并不需要保留这些提交记录...

**「此项目可以帮助你对你的仓库历史提交记录进行修剪，通过变基剪枝的方式来删除你所不需要的部分历史提交记录，以此减小仓库体积或删除敏感数据」**

## 注意事项：
1.如果 [ [v2.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v2) ] 版本都无法在你巨大的仓库运行，可以尝试该版本——此版本是 [ [v2.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v2) ] 版本的变种，该版本无法在原有仓库的基础上保留任何历史提交，会强制删除所有历史提交，并以文件为单位重新`Push`。因此该版本对仓库或文件夹容量没有限制要求，只要你单个文件小于2G即可，但代价就是每个文件都涉及到`Push`，这将导致该脚本的执行速度非常缓慢，大概是 [ [v2.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v2) ] 版本速度的五分之一，并且在你执行完此脚本后，该分支会有大量的单文件`Commit`记录（你的项目中有多少文件就有多少条记录）。

2.执行此项目后，原始提交记录将完全丢失，会自动生成以每个文件为单位的`Push`记录。

## 运行示例：
[ 下图为该示例分支中，执行脚本后会呈现的完整历史记录提交状态 ]
![image](https://github.com/Container-Zero/Branch-Pruner-Action/assets/20435019/1c7fa242-d2f3-4450-862b-442f4edcd12f)

## 使用方法：
1.**为了防止意外情况，请在操作前备份你的仓库，或新建一个临时仓库进行脚本实验，确保功能符合你的需求。**

2.首先需要赋予`Github Action`权限——前往要清理历史记录的仓库，依次点击 `Settings`-`Actions`-`General` 找到 `Workflow permissions` 中的 `Allow GitHub Actions to create and approve pull requests` 与 `Read and write permissions` 选项，将其勾选并保存。

3.拉取该分支内的`branch_pruner_v3.0.yml`文件，并在`Github Action`中保存，保持命名为`branch_pruner_v3.0.yml`并执行此Action。


