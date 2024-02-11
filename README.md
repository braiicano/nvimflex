<<<<<<< HEAD
# nvimflex
Fast custom terminal and neovim like ide
=======
<div style="padding: 1.5rem">
<style>
*{
    scroll-behavior: smooth;
}
div.mk-center{
    display: grid;
    place-items: center;
}
div.text-center{
    text-align: center;
}
</style>

# Faster Customizer

This repo help you to customize your terminal and hyperextensible text editor for your terminal

---

### How will install we?

Step by step, to install it [manually](#manually) or [automatically](#automatic)

### [What](#what) will install we?

<div class="mk-center">

|*Terminal*| *Applications* | *IDE* |
|:--:|:--:|:--:|
|ZSH|Curl| Neovim|
|Oh-my-zsh|Git|Lazy.nvim|
|Powerlevel10k|Python3|Treexplorer|
|NerdFont|Pip3|Shorthands|
|***Plugins***|Nodejs|***Dependencies***|
|Autocomplete|Live-server|Telescope|
|Autosuggestions||LSPs|
|Highlighting||nvim-cmp|

</div>

---

<div id="automatic">

## Auto-install

</div>

>![TIP]
> Verify cURL have installed in your system**

To install cURL:

```sh
# Use your package installer
sudo apt install curl
```

To more information: Click here in *[Documentation](https://curl.se/)*.

### Execute to auto-install

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/braiicano/neovimflex/termflex)"
```

#### Or download *[installer](https://raw.githubusercontent.com/braiicano/neovimflex/termflex)* and run


```sh
./Downloadfolder/termflex
```

<div id="manually">

## Manual

</div>

In references links are all sources to install manually the programs

*Step by step for install:*

#### For terminal

- ZSH and tools:

    - Install ZSH
    ```sh
    sudo apt install -y zsh
    ```
    - Install Oh-My-Zsh
    ```sh
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

    ```
    - Install NerdFonts <[Font Lists](https://www.nerdfonts.com/font-downloads)>
    ```sh
    curl -fLo "<FONT NAME> Nerd Font Complete.otf" 
    https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/<FONT_PATH>/complete/<FONT_NAME>%20Nerd%20Font%20Complete.otf
    ```
    - Install Powerlevel10k
    ```sh
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```
    - *Plugins:*
        
        - Autocomplete
        ```sh
        git clone https://github.com/marlonrichert/zsh-autocomplete $HOME/.oh-my-zsh/custom/plugins/zsh-autocomplete
        ```
        - Autosuggestions
        ```sh
        git clone https://github.com/zsh-users/zsh-autosuggestions $HOME/.oh-my-zsh/custom/plugins/zsh-autosuggestions
        ```
        - Highlighting
        ```sh
        git clone https://github.com/zsh-users/zsh-syntax-highlighting $HOME/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
        ```
        

---
    
#### Tools

- cURL
    - ``sudo apt install curl -y``
- GIT
    - ``sudo apt install git -y``
- Python3
    - ``sudo apt install python3 python3-pip`` 
- Nodejs
    - ```sudo apt install nodejs && sudo npm install -g live-server``` 

---
#### IDE


- Neovim
 
 
   - Install neovim:
        - ``sudo apt install neovim``
    - Install nvim.flex
        -  ``git clone https://github.com/braiicano/nvimflex "$HOME/.config/nvim"``
- Dependencies
    - Lazy.nvim
        - Make init file 
        ```lua
        cat << EOF > "$HOME/.config/nvim/init.lua"
        --Install first time Lazy
        local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
        if not vim.loop.fs_stat(lazypath) then
        vim.fn.system({
            "git",
            "clone",
            "--filter=blob:none",
            "https://github.com/folke/lazy.nvim.git",
            "--branch=stable", -- latest stable release
            lazypath
        })
        end
        vim.opt.rtp:prepend(lazypath)
        
        --To use Lazy
        require("lazy").setup("nvimflex.plugins")
        EOF
        ```
    - Nvim-treesiter
        ```lua
        cat << EOF > "$HOME/.config/nvim/nvimflex/plugins/treesiter.lua
        return{
            "nvim-treesitter/nvim-treesitter",
            dependencies = {
            "nvim-treesitter/nvim-treesitter-textobjects",
            },
            build = ":TSUpdate",
            event = "VeryLazy",
        }
        EOF
        ```
    - Plenary.nvim
        
        ```Installing automatic when charge Telescope```
    - Telescope
        
        ```lua
        cat << EOF > "$HOME/.config/nvim/nvimflex/plugins/telescope.lua"
        return {
            "nvim-telescope/telescope.nvim",
            tag = "0.1.5",
            dependencies = { 'nvim-lua/plenary.nvim' }

        }
        EOF
        ```
    - nvim-lspconfig ``LSP is incluyed in Neovim``
        - View [Servers Config](https://github.com/neovim/nvim-lspconfig/blob/master/doc/server_configurations.md) 
    - nvim-cmp
        
        ```lua
        cat << EOF > "$HOME/.config/nvim/nvimflex/plugins/cmp.lua"
        return{
            "hrsh7th/nvim-cmp",
            dependencies = {
                "neovim/nvim-lspconfig",
                "hrsh7th/cmp-nvim-lsp",
                "hrsh7th/cmp-buffer",
                "hrsh7th/cmp-path",
                "hrsh7th/cmp-cmdline",
                "hrsh7th/nvim-cmp",
                "L3MON4D3/LuaSnip",
                "saadparwaiz1/cmp_luasnip",
            }
        }
        EOF
        ```


### For more plugins or tools visit github repositories

<div class="text-center">

[hrsh7th/nvim-cmp](https://github.com/hrsh7th/nvim-cmp)

[nvim-telescope/telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)

[nvim-treesitter/nvim-treesiter](https://github.com/nvim-treesitter/nvim-treesitter)

[neovim/nvim-lspconfig](https://github.com/neovim/nvim-lspconfig)

[Color scheme](https://github.com/topics/neovim-colorscheme)

[More plugins](https://dotfyle.com/neovim/plugins/trending0)

</div>

---
<div id="what">

### References links

<div class="mk-center">

|Name|Link|Description|
|:-:|:-:|:-|
|Zsh|[Source](https://zsh.sourceforge.io/Arc/git.html)|Is an interactive and it is also a powerful scripting language
|Oh my zsh|[Github](https://github.com/ohmyzsh/ohmyzsh/)|Is a framework for managing *zsh*
|Powerlevel10k|[Github](https://github.com/romkatv/powerlevel10k)|Is a theme for *zsh*
|Nerd Fonts|[Web](https://www.nerdfonts.com/)|Iconic font aggregator, collection, and patcher
|Autocomplete|[Github](https://github.com/marlonrichert/zsh-autocomplete)|For **autocomplete** in real time
|Autosuggestion|[GIthub](https://github.com/zsh-users/zsh-autosuggestions)|It suggests commands as you type based on history and completions
|Highlighting|[Github](https://github.com/zsh-users/zsh-syntax-highlighting)|This provides syntax highlighting for the shell zsh
|||
|cURL|[Web](https://curl.se/)|cmd line tool and library for transferring data with URLs
|GIT|[Web](https://git-scm.com/)|For version controls
|Python3|[Web](https://www.python.org/)|It's a programming language that lets you work quickly
|Pip3|[Web](https://pypi.org/project/pip/)|Package manager for python
|Node js|[Web](https://nodejs.org/en)|Cross-platform JavaScript runtime environment
|Live-server|[Source](https://www.npmjs.com/package/live-server)|This is a little development server with live reload capability
|||
|Neovim|[Web](https://neovim.io/)|Hyperextensible Vim-based text editor
|Lazy.nvim|[Github](https://github.com/folke/lazy.nvim)|Is a modern plugin manager for Neovim
|Telescope|[GIthub](https://github.com/nvim-telescope/telescope.nvim)|Is a highly extendable fuzzy finder over lists
|Treesitter|[Github](https://github.com/nvim-treesitter/nvim-treesitter)|Highlight parser tool for neovim
|LSP|[Github](https://github.com/neovim/nvim-lspconfig)|Language Server Program for neovim
|nvim-cmp|[Github](https://github.com/hrsh7th/nvim-cmp)|A completion engine plugin for neovim


</div>
</div>
</div>

>>>>>>> 1276f89 (create init)
