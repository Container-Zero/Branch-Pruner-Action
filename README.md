# branch-pruner-action  v2.0
## 这是什么：
1.有的时候，你不小心`Push`了一些敏感数据，你希望清除历史提交记录以抹除这些数据，但你又无法回滚或者不希望因此重建这个仓库...

2.随着你对仓库的不断`Push`，历史提交记录将会不断堆积，仓库的体积也随之上升。有的时候不断增大的体积可能会对你造成困扰，而你只是个人项目，并不需要保留这些提交记录...

**「此项目可以帮助你对你的仓库历史提交记录进行修剪，通过变基剪枝的方式来删除你所不需要的部分历史提交记录，以此减小仓库体积或删除敏感数据」**

## 注意事项：
1.注意！该版本并不是 [ [v1.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v1) ] 的升级版本，二者之区别只限于实现方式的不同，该版本无法在原有仓库的基础上保留任何历史提交，会强制删除所有历史提交并以文件夹为单位重新`Push`。因此此脚本不在受限于单个仓库小于2G硬性需求，而是单个文件夹根目录下的文件小于2G即可（不包含文件夹内子文件夹的大小）

2.执行此项目后，原始提交记录将完全丢失，会自动生成以仓库中文件夹为单位的`Push`记录。

3.**再次强调，该版本不同于 [ [v1.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v1) ] 版本，仅适用于你的仓库非常的巨大，并且你完全不需要保留任何原始历史提交记录时，才该尝试使用。除此之外的情况你应该使用 [ [v1.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v1) ] 的版本。什么？你说这个版本还无法在你巨大的仓库执行？来试试 [ [v3.0](https://github.com/Container-Zero/Branch-Pruner-Action/tree/v3) ] 版本吧...**

## 使用方法：
1.**为了防止意外情况，请在操作前备份你的仓库，或新建一个临时仓库进行脚本实验，确保功能符合你的需求。**

2.首先需要赋予`Github Action`权限——前往要清理历史记录的仓库，依次点击 `Settings`-`Actions`-`General` 找到 `Workflow permissions` 中的 `Allow GitHub Actions to create and approve pull requests` 与 `Read and write permissions` 选项，将其勾选并保存。

3.拉取该分支内的`branch_pruner_v2.0.yml`文件，并在`Github Action`中保存，保持命名为`branch_pruner_v2.0.yml`并执行此Action。


