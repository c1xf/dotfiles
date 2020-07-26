# Dotfiles

> 原文 [How to manage your dotfiles with git](https://medium.com/toutsbrasil/how-to-manage-your-dotfiles-with-git-f7aeed8adf8b)

## 初始化

```bash
git init --bare $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no
// .zshrc or .bashrc
echo "alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.zshrc
```

## 更新配置

```bash
dotfiles status
dotfiles add .vimrc
dotfiles commit -m "Add vimrc"
dotfiles add .bashrc
dotfiles commit -m "Add bashrc"
dotfiles push
```

## 拉取

```bash
git clone --bare repository(https://github.com/$xxx/dotfiles.git) $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles checkout
```

## Apps

### Rime

中文输入，英文输入还是用 mac 自带输入法

- 修改 app_options
- 修改 `switches/@0/reset: 0` `switches/@0/states: [中文]`

下载管理工具

```bash
/Library/Input\ Methods/Squirrel.app/Contents/MacOS/rime-install
.../rime_dict_manager
```

错误日志

```bash
$TMPDIR/rime.Squirrel.
```

- Fn + Shift + delete 去掉错误的词
