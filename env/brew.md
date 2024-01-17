# Homebrew

> Homebrew 是mac的软件管理器，用于下载存在依赖关系的软件包。通过 Homebrew 下载的软件都来自于官网，绝对放心软件的安全性。而且它尽可能地利用系统自带的各种库，使得软件包的编译时间大大缩短，基本上不会造成冗余。

## 安装

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

```brew -v ``` 查看是否安装成功

## 切换源

### 查看当前源
- brew.git （源代码仓库）
- homebrew-core.git （核心软件仓库）
- homebrew-bottles （预编译二进制软件包）

```
# 查看brew镜像源
git -C "$(brew --repo)" remote -v
# 查看homebrew-core镜像源
git -C "$(brew --repo homebrew/core)" remote -v
# 查看homebrew-cask镜像源（需要安装后才能查看）
git -C "$(brew --repo homebrew/cask)" remote -v 
```

### 修改源
```
# 替换brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.ustc.edu.cn/brew.git
 
# 替换homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
 
# 替换homebrew-cask.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-cask"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-cask.git
 
# 应用生效
brew update
# 替换homebrew-bottles:
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile
```

## 常用指令

- 版本号brew -v 
- 更新brew  update
- 本地软件库列表：brew list
- 查看软件库版本：brew list --versions
- 查找软件包：brew search xxx （xxx为要查找软件的关键词）
- 安装软件：brew cask install xxx（xxx为软件名称）
- 卸载软件：brew cask uninstall xxx
- 清理所有旧版本包  brew cleanup
- 列出所有旧版本包  brew cleanup -n
- 查看一安装软件的依赖  brew deps -installed  --tree

使用arm 版本brew，直接brew即可
使用intel版本brew， arch -x86_64 /usr/local/bin/brew

## 安装位置
M1版本的Homebrew默认安装在/opt/homebrew目录下
如果你在M1芯片的Mac上运行的是x86版本的Homebrew，它通常安装在/usr/local目录下