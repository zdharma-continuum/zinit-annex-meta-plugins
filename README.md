# Meta-Plugins support for Zsh-Zinit

### **Install groups of plugins via a single, friendly label …**
### **… and also have the curated, optimal ice lists automatically applied !**

![screenshot](https://raw.githubusercontent.com/zdharma-continuum/zinit-annex-meta-plugins/master/images/fuzzy-mplg-ex.png)

## Rationale

It can be tiring to:
1. Constantly, over and over collect some new interesting plugins to install/load.
2. Over and over reconstruct the new findings on the new machines.
3. Constantly extend and tweak the ice list of each plugin, so that it's hard on
  eyes, especially for an outsider.

Meta-Plugins annex helps in those problems:

| Problem                   | Solution |
|:-------------------------:|----------|
| (1)<br/> *finding new plugins*                              | the annex contains a curated, broad list of plugins, e.g.: all the console tools like `fd`, `fzf`, `exa`, `ripgrep`, etc., |
| (2)<br/> *reconstructing the findings in new environments*     | it's easy to say and memorize e.g.: `zinit for console-tools` – one label pulls a group of plugins and also the curated, optimal, default ice lists for each of them, |
| (3)<br/> *constant increase of complexity of the commands*  | the provided, hopefully best/optimal ices for each plugin are handled transparently and automatically; care is given to each ice list so that the plugin loads without any glitches (e.g.: without "No files for compilation found." message and other, even such slight issues). |

Other unique benefits of the Meta-Plugins annex:

| Benefit                   | Description |
|:-------------------------:|-------------|
|plugin dependencies                                            | The meta-plugins implement a dependency mechanism (to some extent), so that e.g.: selecting a from-source built [ogham/exa](https://github.com/ogham/exa) will automatically pull-in also the Rust compiler (available under meta-plugin name: `rust-toolchain`). |
|flexible disabling of chosen sub-plugins in any meta-plugin    | A meta-plugin can contain many sub-plugins and it's possible to skip installing some of them by the **skip'plg-1 plg-2…'** ice, e.g.: `zinit skip'ripgrep fd' for console-tools`. This way despite that some of the meta-plugins are broad the user still has control over what's and how much is being installed.|
|common from-source meta-plugins                                | For the plugins that provide the binary programs it is often the case that a meta-plugin exists that'll build the program from source (e.g.: **fuzzy** meta-plugin and its **fuzzy-src** counterpart). This might be handy e.g.: if there's no binary for our machine. |

## The list of the meta-plugins

|Meta-Plugin ID     | Contained sub-plugins |
|:-----------------:|-----------------------|
|**annexes**        |[zdharma-continuum/zinit-annex-unscope](https://github.com/zdharma-continuum/zinit-annex-unscope), [zdharma-continuum/zinit-annex-as-monitor](https://github.com/zdharma-continuum/zinit-annex-as-monitor), [zdharma-continuum/zinit-annex-patch-dl](https://github.com/zdharma-continuum/zinit-annex-patch-dl), [zdharma-continuum/zinit-annex-rust](https://github.com/zdharma-continuum/zinit-annex-rust), [zdharma-continuum/zinit-annex-submods](https://github.com/zdharma-continuum/zinit-annex-submods), [zdharma-continuum/zinit-annex-bin-gem-node](https://github.com/zdharma-continuum/zinit-annex-bin-gem-node)                        | 
|**annexes+con**    |[zdharma-continuum/zinit-console](https://github.com/zdharma-continuum/zinit-console), annexes (**meta-plugin**)                 |
|                   |                                                 |
|**zsh-users**      |[zsh-users/zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting), [zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions), [zsh-users/zsh-completions](https://github.com/zsh-users/zsh-completions)        |
|**zsh-users+fast**, |[zdharma-continuum/fast-syntax-highlighting](https://github.com/zdharma-continuum/fast-syntax-highlighting), [zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions), [zsh-users/zsh-completions](https://github.com/zsh-users/zsh-completions)         |
|                   |                                                 |
|**zdharma**        |[zdharma-continuum/fast-syntax-highlighting](https://github.com/zdharma-continuum/fast-syntax-highlighting), [zdharma-continuum/history-search-multi-word](https://github.com/zdharma-continuum/history-search-multi-word), [zdharma-continuum/zsh-diff-so-fancy](https://github.com/zdharma-continuum/zsh-diff-so-fancy)     |
|**zdharma2**       |[zdharma-continuum/zconvey](https://github.com/zdharma-continuum/zconvey), [zdharma-continuum/zui](https://github.com/zdharma-continuum/zui), [zdharma-continuum/zflai](https://github.com/zdharma-continuum/zflai)        |
|                   |                                                 |
|**molovo**         |[molovo/color](https://github.com/molovo/color), [molovo/revolver](https://github.com/molovo/revolver), [molovo/zunit](https://github.com/molovo/zunit)        |
|                   |                                                 |
|**sharkdp**        |[sharkdp/fd](https://github.com/sharkdp/fd), [sharkdp/bat](https://github.com/sharkdp/bat), [sharkdp/hexyl](https://github.com/sharkdp/hexyl), [sharkdp/hyperfine](https://github.com/sharkdp/hyperfine), [sharkdp/vivid](https://github.com/sharkdp/vivid)             |
|                   |                                                 |
|**developer**      |[github-issues](https://github.com/Zsh-Packages/github-issues) (**package**), [github-issues-srv](https://github.com/Zsh-Packages/github-issues-srv) (**package**), [molovo/color](https://github.com/molovo/color), [molovo/revolver](https://github.com/molovo/revolver), [molovo/zunit](https://github.com/molovo/zunit), [voronkovich/gitignore](https://github.com/voronkovich/gitignore.plugin.zsh), [jonas/tig](https://github.com/jonas/tig)             |
|                   |                                                 |
|**console-tools**  |[dircolors-material](https://github.com/Zsh-Packages/dircolors-material) (**package**), sharkdp (**meta-plugin**), [ogham/exa](https://github.com/ogham/exa), [BurntSushi/ripgrep](https://github.com/BurntSushi/ripgrep), [jonas/tig](https://github.com/jonas/tig), [direnv/direnv](https://github.com/direnv/direnv)|
|                   |                                                 |
|**fuzzy**          |[fzf](https://github.com/Zsh-Packages/fzf) (**package**), [fzy](https://github.com/Zsh-Packages/fzy) (**package**), [lotabout/skim](https://github.com/lotabout/skim), [peco/peco](https://github.com/peco/peco)                  |
|**fuzzy-src**      |fzf-go, [fzy](https://github.com/Zsh-Packages/fzy) (**package**), skim-cargo, peco-go                    |
|                   |                                                 |
|**ext-git**        |[Fakerr/git-recall](https://github.com/Fakerr/git-recall), [paulirish/git-open](https://github.com/paulirish/git-open), [paulirish/git-recent](https://github.com/paulirish/git-recent), [davidosomething/git-my](https://github.com/davidosomething/git-my), [arzzen/git-quick-stats](https://github.com/arzzen/git-quick-stats), [iwata/git-now](https://github.com/iwata/git-now), [tj/git-extras](https://github.com/tj/git-extras), [wfxr/forgit](https://github.com/wfxr/forgit)  |
|                   |                                                 |
|**rust-utils**     |rust-toolchain, cargo-extensions                  |
|                   |                                                 |
|**prezto**         |PZTM::archive, PZTM::directory, PZTM::utility      |

## Example zshrc

```zsh
# Installs total of 22 plugins
zinit for annexes zsh-users+fast console-tools fuzzy
```
<!-- vim:set ft=markdown tw=81 fo+=a1n autoindent: -->
