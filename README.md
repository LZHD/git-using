# git-using

## git-diffall

> git-diffall(git目录对比) Fork自 [git-diffall](https://github.com/thenigan/git-diffall) 项目

The git-diffall script provides a directory based diff mechanism
for git.

To determine what diff viewer is used, the script requires either
the 'diff.tool' or 'merge.tool' configuration option to be set.

This script is compatible with most common forms used to specify a
range of revisions to diff:

  1. git diffall: shows diff between working tree and staged changes
  2. git diffall --cached [<commit>]: shows diff between staged
     changes and HEAD (or other named commit)
  3. git diffall <commit>: shows diff between working tree and named
     commit
  4. git diffall <commit> <commit>: show diff between two named commits
  5. git diffall <commit>..<commit>: same as above
  6. git diffall <commit>...<commit>: show the changes on the branch
     containing and up to the second, starting at a common ancestor
     of both <commit>

Note: all forms take an optional path limiter [-- <path>*]

The '--extcmd=<command>' option allows the user to specify a custom
command for viewing diffs.  When given, configured defaults are
ignored and the script runs $command $LOCAL $REMOTE.  Additionally,
$BASE is set in the environment.

This script is based on an example provided by Thomas Rast on the
Git list [1]:

[1] http://thread.gmane.org/gmane.comp.version-control.git/124807

>* 配置（config）
```sh
    git config --global diff.tool meld #配置默认的difftool
    git config --global merge.tool meld #配置默认的mergetool
    sudo ln -s /home/yourpath/git-diffall /usr/local/bin/git-diffall #通过软链接建立系统命令
    git config --global alias.diffall git-diffall #添加git别名执行git-diffall功能
```
