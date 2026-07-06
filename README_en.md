# dotfiles-freebsd 

**Warning:** This is my personal FreeBSD 15 configuration. 
It is recommended to use it only as inspiration, as there is no guarantee that it will work for you. 
It was built on my machine, and on my machine it works. 

**dwm + st + dwmblocks + picom + dunst** 

There are also a few useful scripts to get Discord, virtual machines, 
and a few other things working. ## Wallpaper The ASCII daemon wallpaper is included in `wallpapers/`. 
Originally from Wallhaven. 

## Patches 

### dwm 

- **vanitygaps** — configurable gaps between windows 
- **status2d** — colored status bar via escape sequences 
- **fancybar** — active window title in the status bar 
- **swallow** — terminals swallow spawned GUI applications 
- **cfacts** — resize individual windows in the stack 
- **scratchpad** — floating terminal with a keybinding 
- **movestack** — move windows up and down in the stack 
- **xresources** — load colors and configuration dynamically from Xresources

### st 

- **HarfBuzz** — advanced font rendering 
- **alpha** — background transparency 
- **scrollback** — keyboard and mouse scrollback support 
- **externalpipe** — pipe terminal output to external commands 
- **boxdraw** — improved line-drawing character rendering 
- **xresources** — load colors from Xresources 


## Dynamic Color Scheme 

The `scripts/newlook` script randomly changes the wallpaper and regenerates the entire desktop color scheme using `pywal`: 

1. Selects a random wallpaper from `~/pix/wall/` and applies it with `xwallpaper`
2. `pywal` generates a color palette from the wallpaper
3. The colors are merged into dwm's Xresources using `xrdb`
4. `killall -USR1 dwm` reloads the colors in dwm without restarting it The dwm status bar, window borders, and the terminal (`st`) automatically update their color scheme to match the selected wallpaper.


## Dependencies 
| Program      | Purpose                                     | 
|--------------|---------------------------------------------| 
| `xwallpaper` | wallpaper management                        | 
| `pywal`      | dynamic color schemes                       | 
| `dmenu`      | application launcher                        | 
| `picom`      | compositor (transparency, blur, animations) | 
| `dunst`      | notifications                               | 
| `flameshot`  | screenshots                                 | 
| `xrandr`     | monitor configuration                       |
