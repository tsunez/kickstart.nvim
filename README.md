## Introduction

My personal neovim configuration.

## Installation

### Install Neovim

Kickstart.nvim targets *only* the latest
['stable'](https://github.com/neovim/neovim/releases/tag/stable) and latest
['nightly'](https://github.com/neovim/neovim/releases/tag/nightly) of Neovim.
If you are experiencing issues, please make sure you have the latest versions.

### Install External Dependencies

External Requirements:
- Basic utils: `git`, `make`, `unzip`, C Compiler (`gcc`)
- [ripgrep](https://github.com/BurntSushi/ripgrep#installation)
- Clipboard tool (xclip/xsel/win32yank or other depending on platform)
- A [Nerd Font](https://www.nerdfonts.com/): optional, provides various icons
  - if you have it set `vim.g.have_nerd_font` in `init.lua` to true
- Language Setup:
  - If want to write Typescript, you need `npm`
  - If want to write Golang, you will need `go`
  - etc.

> **NOTE**
> See [Install Recipes](#Install-Recipes) for additional Windows and Linux specific notes
> and quick install snippets

### Install Kickstart

Neovim's configurations are located under the following paths, depending on your OS:

| OS | PATH |
| :- | :--- |
| Linux, MacOS | `$XDG_CONFIG_HOME/nvim`, `~/.config/nvim` |
| Windows (cmd)| `%localappdata%\nvim\` |
| Windows (powershell)| `$env:LOCALAPPDATA\nvim\` |

### Install Lazy.nvim

This is step 1, you need [this](https://lazy.folke.io) to install the rest of the modules.

[Lazy loading](https://lazy.folke.io/spec/lazy_loading) does what its name implies, it only loads plugins when they are needed. The behavior can be tuned:

* The plugin only exists as a dependency in your spec
* It has an event, cmd, ft or keys key
* config.defaults.lazy = true

Colorschemes can be configured to load automatically lazy=true. I think its possible to [load more](https://lazy.folke.io/spec/examples) then one color scheme an prioritize the order they are applied in??

Its recommended to check the (lazy-lock.json) file in, it will be used to ensure your plugins are all at the same version wherever you clone the project. To update all of your plugins to the same version:
```sh
:lazy restore
```

It appears that Lazy.nvim has support of luarocks, among other package formats. It's possible to disable luarocks support

### Install Colorscheme

### Treesitter

This handles the color highlighting for your code

[Tree sitter playground](https://github.com/nvim-treesitter/playground). This lets you see the treesitter formatting codes directly in nvim

### Install telescope

### Install LSP

### Install Color Theme

### Install harpoon

[Harpoon](https://github.com/ThePrimeagen/harpoon/tree/harpoon2), Allows you to tag files you find you're using frequently so you can find them quick..

### Interesting extensions

[banana.nvim](https://github.com/CWood-sdf/banana.nvim) is an inline HTML render, this might be a good model for my markdown tool?


### Lua Notes

[LuaRocks](https://luarocks.org) is the package manager for Lua modules.



### Wezterm

[Wezterm](https://wezfurlong.org/wezterm/index.html)

This covers how I configure my terminal environment...todo


### Post Installation

That's it! Lazy will install all the plugins you have. Use `:Lazy` to view
current plugin status. Hit `q` to close the window.

Read through the `init.lua` file in your configuration folder for more
information about extending and exploring Neovim. That also includes
examples of adding popularly requested plugins.


### Getting Started

[The Only Video You Need to Get Started with Neovim](https://youtu.be/m8C0Cq9Uv9o)

### FAQ

* Can I keep my existing configuration in parallel to kickstart?
  * Yes! You can use [NVIM_APPNAME](https://neovim.io/doc/user/starting.html#%24NVIM_APPNAME)`=nvim-NAME`
    to maintain multiple configurations. For example, you can install the kickstart
    configuration in `~/.config/nvim-kickstart` and create an alias:
    ```
    alias nvim-kickstart='NVIM_APPNAME="nvim-kickstart" nvim'
    ```
    When you run Neovim using `nvim-kickstart` alias it will use the alternative
    config directory and the matching local directory
    `~/.local/share/nvim-kickstart`. You can apply this approach to any Neovim
    distribution that you would like to try out.
  * Discussions on this topic can be found here:
    * [Restructure the configuration](https://github.com/nvim-lua/kickstart.nvim/issues/218)
    * [Reorganize init.lua into a multi-file setup](https://github.com/nvim-lua/kickstart.nvim/pull/473)

</details>
#### Linux Install
<details><summary>Ubuntu Install Steps</summary>

```
sudo add-apt-repository ppa:neovim-ppa/unstable -y
sudo apt update
sudo apt install make gcc ripgrep unzip git xclip neovim
```
</details>

