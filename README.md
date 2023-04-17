# neovim 配置过程

## 版本

此配置过程所需 neovim 最低版本为 0.8.2

## 配置文件位置 

neovim 会自动加载 ~/.config/nvim/init.lua

lua 是一种脚本语言，neovim 使用此语言进行配置，好处是可以使得配置模块化。

~/.config/nvim/lua/core/ 文件夹下的 lua 文件即是 neovim 的模块化配置，这里的文件需要被 ~/.config/nvim/init.lua 引入

- ~/.config/nvim/lua/core/options.lua 是 neovim 的选项功能配置
- ~/.config/nvim/lua/core/keymaps.lua 是 neovim 的快捷键配置

## neovim 的选项配置

此节描述 ~/.config/nvim/lua/core/options.lua 配置的功能，具体的功能参数请参考配置文件中的注释，这里只说明开启了哪些
功能。

- 开启行号和相对行号
- 缩进配置 e
- 
