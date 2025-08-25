+++
title = 'Dev Setup Zellij'
date = 2025-08-26T00:56:21+05:30
draft = false
+++
Using [Zellij](https://zellij.dev/) I am able to quickly setup my dev environment.

3 Tabs
- [Yazi File Manager](https://yazi-rs.github.io/)
- [NVIM](https://neovim.io/)
- [Lazygit](https://github.com/jesseduffield/lazygit/)

These three tabs open up with a single command `zs`

I have created an alias for the following
`alias zs="zellij --layout ~/.config/zellij/my-dev-setup.kdl"`

The file `my-dev-setup.kdl` is:
```kdl
layout {
    default_tab_template {
        children
        pane size=1 {
            plugin location="zellij:compact-bar"
            borderless true
        }
    }

    tab name="Yazi" {
        pane command="yazi" close_on_exit=true {
            borderless true 
        }
    }

    tab name="nvim" {
        pane borderless=true {
            command "nvim"
            args "."
        }
    }

    tab name="lazygit" {
        pane borderless=true command="lazygit" close_on_exit=true
    }
}
```

Yazi
![Yazi](https://i.postimg.cc/ZTWvgT6C/screenshot-2025-08-26-00-59-56.png)

NVIM
![NVIM](https://i.postimg.cc/T26ypgFD/screenshot-2025-08-26-01-00-07.png)

Lazygit
![Lazygit](https://i.postimg.cc/w9G7DSnH/screenshot-2025-08-26-01-00-20.png)


