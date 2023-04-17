# neovim 配置过程

## 版本

此配置过程所需 neovim 最低版本为 0.8.2

## 配置文件位置 

neovim 会自动加载 ~/.config/nvim/init.lua

lua 是一种脚本语言，neovim 使用此语言进行配置，好处是可以使得配置模块化。

~/.config/nvim/lua/core/ 文件夹下的 lua 文件即是 neovim 的模块化配置，这里的文件需要被 ~/.config/nvim/init.lua 引入

~/.config/nvim/lua/plugins/ 文件夹下的 lua 文件时 neovim 的插件配置，这里的配置文件同样需要被 ~/.config/nvim/init.lua 引入

## neovim 的选项配置

此节描述 ~/.config/nvim/lua/core/options.lua 配置的功能，具体的功能参数请参考配置文件中的注释，这里只说明开启了哪些
功能。

- 开启行号和相对行号
- 缩进配置 e
- 不开启 wrap
- 光标行的明显提示
- 开启鼠标
- 开启新窗口时默认的位置
- 搜索时忽略大小写，但若只搜索大写，则只搜索大写，不会搜索小写
- 开启终端真色

## neovim 的快捷键映射

此节描述 ~/.config/nvim/lua/core/keymaps.lua 配置的功能，具体配置参数请参考配置文件中的注释。

- 设置 leader key
- 插入模式中
    - 将 `jk` 设置为推出，即 <esc> 键 
- 视觉模式中
    - 使用 `shift J` 和 `shift K` 批量移动代码块。
- 命令模式中
    - `<leader>sv` 水平增加窗口
    - `<leader>sh` 垂直增加窗口
    - `<leader>nh` 取消搜索高亮


## 插件管理

仅仅依靠修改 neovim 的配置很难完成复杂的功能，所以需要插件的帮助。当插件太多时，插件本身也需要被统一管理。使用 packer 管理插件是很好的选择。

packer 自身的配置文件位于 ~/.config/nvim/lua/plugins/packer-plugins-setup.lua
若要安装插件，则需在 `startup` 的回调函数中，使用 `use`，具体用例参考配置文件。

## 插件列表及说明

此节列出安装的插件，并做简要说明。

- wbthomason/packer.nvim packer 自身
- folke/tokynight.vim 主题
- nvim-lualine/lualine.vim 状态栏
    - kyazdani42/nvim-web-devicons 状态栏图标
- nvim-tree/nvim-tree.lua 文档树
    - nvim-tree/nvim-web-devicons 文档树图标
- christoomey/vim-tmux-navigator  用ctl-hjkl来定位窗口
- nvim-treesitter/nvim-treesitter  语法高亮
- p00f/nvim-ts-rainbow 不同括号颜色区分,此插件依赖 treesitter
- lsp (Language Server Protocol) 语言服务，提供语法提示, lsp 需要三个插件。
    - williamboman/mason.nvim
    - williamboman/mason-lspconfig.nvim   这个相当于mason.nvim和lspconfig的桥梁
    - neovim/nvim-lspconfig
  }
- 自动补全
  use "hrsh7th/nvim-cmp"
  use "hrsh7th/cmp-nvim-lsp"
  use "L3MON4D3/LuaSnip" -- snippets引擎，不装这个自动补全会出问题
  use "saadparwaiz1/cmp_luasnip"
  use "rafamadriz/friendly-snippets"
  use "hrsh7th/cmp-path" -- 文件路径

  use "numToStr/Comment.nvim" -- gcc和gc注释
  use "windwp/nvim-autopairs" -- 自动补全括号

  use "akinsho/bufferline.nvim" -- buffer分割线
  use "lewis6991/gitsigns.nvim" -- 左则git提示

  use {
    'nvim-telescope/telescope.nvim', tag = '0.1.1',  -- 文件检索
    requires = { {'nvim-lua/plenary.nvim'} }
  }


















