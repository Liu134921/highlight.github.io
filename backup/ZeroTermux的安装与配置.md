# 安装及配置

1. 使用链接: [IXCM工作室下载站](https://od.ixcmstudio.cn/repository/main/)下载ZeroTermux
2. 下载完成后，用音量加或在屏幕左侧连点两下来打开左侧菜单
3. 点击切换源，推荐NJU源或清华源
4. 更改虚拟键盘:
```sh
#! ~/.termux/termux.properties
extra-keys = [ \['ESC','<','>','BACKSLASH','=','^','$','()','{}','[]','ENTER'], \
['TAB','&',';','/','~','%','*','HOME','UP','END','PGUP'], \
['CTRL','FN','ALT','|','-','+','QUOTE','LEFT','DOWN','RIGHT','PGDN'] \
]
```
5. **安装zsh,git,curl** 使用 ` apt install zsh git curl lsd -y` 安装
6. **切换默认Shell**: `chsh -s ~/../usr/bin/zsh`
7. 镜像源安装:
	1. **curl**: `	sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"`
	2. **wget**: `sh -c "$(wget -O- https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"`
8. 安装插件:
	1. **zsh-autosuggestions**: `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
	2. **zsh-syntax-highlighting**: `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
9. 更改配置: 
```sh
#! ~/.zshrc

# Oh-my-zsh启动设置
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="bira" # 设置主题为bira
plugins=(git zsh-autosuggestions zsh-syntax-highlighting z extract web-search) # 启用插件
source $ZSH/oh-my-zsh.sh # 启动Oh-my-zsh

# Shell别名函数设置
alias ls=lsd
alias lt="lsd --tree"
# 定义函数：安装 apt 包
pi() {
  apt install "$@"
}

# 定义函数：搜索 apt 包
ps() {
  apt search "$@"
}

# 定义函数：卸载 apt 包
pu() {
  apt remove "$@"
}
# 定义函数：强制删除文件/目录
rf() {
  rm -rf "$@"
}
```
# 完成基本配置
从这里开始，已经完成了基本配置，再安装MapleMono字体就差不多了
