# git-using
> Git 常用命令及脚本

## git目录对比

> [配置(config)](https://github.com/LZHD/git-diffall)

```sh
git config --global diff.tool meld #配置默认的difftool
git config --global merge.tool meld #配置默认的mergetool
sudo ln -s /home/yourpath/git-diffall /usr/local/bin/git-diffall #通过软链接建立系统命令
git config --global alias.diffall git-diffall #添加git别名执行git-diffall功能
```

## 修改git历史记录

> [参考(reference)](https://help.github.com/articles/changing-author-info/)

```sh
git clone --bare https://github.com/user/repo.git
cd repo.git
sh ./git-author-rewrite.sh
git push --force --tags origin 'refs/heads/*'
```
