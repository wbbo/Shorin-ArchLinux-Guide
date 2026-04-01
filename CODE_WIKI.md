# ShorinArchExperience 项目仓库文档

## 1. 项目概述

本项目是一个关于Arch Linux系统配置和使用的个人实践经验仓库，旨在为初学者提供一个全面的指南，帮助他们快速上手Arch Linux系统。项目包含了从系统安装到日常使用的各种配置和技巧，涵盖了多种桌面环境和Wayland合成器的配置。

### 1.1 项目目标

- 提供详细的Arch Linux安装指南（手动和脚本安装）
- 分享多种桌面环境和Wayland合成器的配置方案
- 提供游戏、虚拟机、输入法等常用功能的配置方法
- 分享系统性能调优和美化技巧

## 2. 目录结构

项目采用清晰的目录结构，将不同类型的配置和资源分开管理：

```
├── dotfiles/          # 各种应用程序和桌面环境的配置文件
├── legacy/            # 旧的配置文件
├── nixos/             # NixOS的配置文件
├── pictures/          # 截图和图片
├── wallpapers/        # 壁纸
├── .gitignore         # Git忽略文件
├── LICENSE            # 许可证文件
├── README.md          # 项目说明
└── 更新日志.md        # 项目更新记录
```

### 2.1 主要目录说明

| 目录 | 描述 | 主要内容 |
|------|------|----------|
| dotfiles/ | 包含各种应用程序和桌面环境的配置文件 | 包含niri、waybar、matugen等应用的配置 |
| legacy/ | 包含旧的配置文件 | 包含Hyprland、foot等旧配置 |
| nixos/ | 包含NixOS的配置文件 | 包含NixOS的系统配置和flake配置 |
| pictures/ | 包含截图和图片 | 项目相关的截图和展示图片 |
| wallpapers/ | 包含壁纸 | 用于桌面背景的壁纸图片 |

## 3. 核心配置模块

### 3.1 Niri Wayland合成器配置

Niri是一个现代化的Wayland合成器，提供类似GNOME的用户体验。项目中包含了详细的Niri配置：

**主要配置文件：**
- [config.kdl](file:///workspace/dotfiles/.config/niri/config.kdl)：主配置文件，包含环境变量、输入设备、启动程序等配置
- [binds.kdl](file:///workspace/dotfiles/.config/niri/binds.kdl)：键盘和鼠标绑定配置
- [colors.kdl](file:///workspace/dotfiles/.config/niri/colors.kdl)：颜色主题配置
- [output.kdl](file:///workspace/dotfiles/.config/niri/output.kdl)：显示输出配置
- [animations.kdl](file:///workspace/dotfiles/.config/niri/animations.kdl)：动画效果配置
- [layout.kdl](file:///workspace/dotfiles/.config/niri/layout.kdl)：窗口布局配置

**核心功能：**
- 自定义键盘快捷键和鼠标行为
- 多显示器支持
- 窗口动画效果
- 自动启动应用程序
- 桌面壁纸管理

### 3.2 Waybar配置

Waybar是一个用于Wayland合成器的高度可定制的状态栏：

**主要配置文件：**
- [config.jsonc](file:///workspace/dotfiles/.config/waybar/config.jsonc)：主配置文件，定义模块布局和位置
- [modules.jsonc](file:///workspace/dotfiles/.config/waybar/modules.jsonc)：模块配置
- [style.css](file:///workspace/dotfiles/.config/waybar/style.css)：样式配置

**核心功能：**
- 工作区显示
- 窗口标题显示
- 系统状态监控（网络、电池、音频等）
- 自定义快捷操作
- 时钟和日期显示

### 3.3 Matugen主题生成器

Matugen是一个基于壁纸生成主题颜色的工具：

**主要配置文件：**
- [config.toml](file:///workspace/dotfiles/.config/matugen/config.toml)：主配置文件
- [templates/](file:///workspace/dotfiles/.config/matugen/templates/)：各种应用程序的主题模板

**核心功能：**
- 基于壁纸自动生成主题颜色
- 支持多种应用程序的主题生成
- 实时主题更新

### 3.4 NixOS配置

项目包含了NixOS的配置文件，用于构建和管理NixOS系统：

**主要配置文件：**
- [configuration.nix](file:///workspace/nixos/configuration.nix)：系统配置文件
- [flake.nix](file:///workspace/nixos/flake.nix)：Flake配置文件

**核心功能：**
- 系统包管理
- 服务配置
- 桌面环境配置
- 用户管理

## 4. 关键脚本和工具

### 4.1 长截图脚本

位于[waybar/scripts/longshot-sh/](file:///workspace/dotfiles/.config/waybar/scripts/longshot-sh/)目录，用于创建长截图：

- [longshot.sh](file:///workspace/dotfiles/.config/waybar/scripts/longshot-sh/longshot.sh)：主脚本
- [stitch.py](file:///workspace/dotfiles/.config/waybar/scripts/longshot-sh/stitch.py)：图片拼接脚本

### 4.2 Niri自动壁纸脚本

位于[niri/scripts/](file:///workspace/dotfiles/.config/niri/scripts/)目录：

- [niri_auto_blur_bg.sh](file:///workspace/dotfiles/.config/niri/scripts/niri_auto_blur_bg.sh)：自动设置模糊背景
- [screenshot.sh](file:///workspace/dotfiles/.config/niri/scripts/screenshot.sh)：截图脚本

### 4.3 Matugen更新脚本

位于[scripts/](file:///workspace/dotfiles/.config/scripts/)目录：

- [matugen-update.sh](file:///workspace/dotfiles/.config/scripts/matugen-update.sh)：更新Matugen主题
- [random-anime-wallpaper.sh](file:///workspace/dotfiles/.config/scripts/random-anime-wallpaper.sh)：随机更换壁纸

## 5. 依赖关系

### 5.1 核心依赖

| 依赖 | 用途 | 安装命令 |
|------|------|----------|
| niri | Wayland合成器 | `pacman -S niri` |
| waybar | 状态栏 | `pacman -S waybar` |
| matugen | 主题生成器 | `pacman -S matugen` |
| fcitx5 | 输入法框架 | `pacman -S fcitx5 fcitx5-chinese-addons` |
| mako | 通知守护进程 | `pacman -S mako` |
| swayosd | 屏幕显示 | `pacman -S swayosd` |
| waypaper | 壁纸管理 | `pacman -S waypaper` |

### 5.2 可选依赖

| 依赖 | 用途 | 安装命令 |
|------|------|----------|
| fastfetch | 系统信息显示 | `pacman -S fastfetch` |
| btop | 系统监控 | `pacman -S btop` |
| fish | 命令行 shell | `pacman -S fish` |
| kitty | 终端模拟器 | `pacman -S kitty` |
| yazi | 文件管理器 | `pacman -S yazi` |
| fuzzel | 应用启动器 | `pacman -S fuzzel` |

## 6. 系统架构

### 6.1 Wayland合成器架构

```
┌─────────────────────────────────────────────────────────┐
│                     应用程序                            │
├─────────────────────────────────────────────────────────┤
│                     Wayland协议                         │
├─────────────────────────────────────────────────────────┤
│  ┌───────────┐  ┌───────────┐  ┌───────────┐  ┌───────────┐
│  │   Niri    │  │  Hyprland │  │ Mangowc  │  │   GNOME   │
│  └───────────┘  └───────────┘  └───────────┘  └───────────┘
├─────────────────────────────────────────────────────────┤
│                硬件抽象层 (libinput)                   │
└─────────────────────────────────────────────────────────┘
```

### 6.2 主题系统架构

```
┌─────────────────────────────────────────────────────────┐
│                       壁纸                              │
├─────────────────────────────────────────────────────────┤
│                      Matugen                            │
├─────────────────────────────────────────────────────────┤
│  ┌───────────┐  ┌───────────┐  ┌───────────┐  ┌───────────┐
│  │   GTK     │  │   Qt      │  │  Waybar   │  │   Mako    │
│  └───────────┘  └───────────┘  └───────────┘  └───────────┘
└─────────────────────────────────────────────────────────┘
```

## 7. 使用指南

### 7.1 系统安装

项目提供了详细的Arch Linux安装指南，包括：
- 手动安装步骤
- 脚本安装方法
- 双系统配置

### 7.2 桌面环境配置

**Niri Wayland合成器配置：**
1. 复制[niri](file:///workspace/dotfiles/.config/niri/)目录到`~/.config/`
2. 安装依赖：`pacman -S niri waybar mako swayosd waypaper`
3. 启动niri：`niri`

**KDE Plasma配置：**
1. 安装KDE Plasma：`pacman -S plasma-meta kde-applications`
2. 配置显示管理器：`systemctl enable sddm`

### 7.3 主题配置

**Matugen主题生成：**
1. 复制[matugen](file:///workspace/dotfiles/.config/matugen/)目录到`~/.config/`
2. 安装matugen：`pacman -S matugen`
3. 运行matugen：`matugen`
4. 自动更新主题：运行`~/.config/scripts/matugen-update.sh`

### 7.4 常用功能配置

**中文输入法：**
- 安装fcitx5：`pacman -S fcitx5 fcitx5-chinese-addons`
- 配置环境变量：在`~/.config/environment.d/`中添加输入法配置

**游戏配置：**
- 安装Steam：`pacman -S steam`
- 安装Lutris：`pacman -S lutris`
- 配置显卡驱动：`pacman -S nvidia nvidia-utils`

**虚拟机配置：**
- 安装VMware：`pacman -S vmware-workstation`
- 安装QEMU/KVM：`pacman -S qemu libvirt virt-manager`

## 8. 性能优化

### 8.1 系统优化

- 使用btrfs文件系统，启用压缩和快照
- 配置swap大小（建议为内存的1.5倍）
- 启用zram交换
- 优化内核参数

### 8.2 游戏优化

- 安装gamemode：`pacman -S gamemode`
- 配置NVIDIA驱动：启用DRM内核模式设置
- 禁用btrfs写时复制（对Steam下载性能提升明显）

### 8.3 启动优化

- 禁用不必要的服务
- 使用systemd-boot引导加载程序
- 配置tmpfs挂载点

## 9. 故障排除

### 9.1 常见问题

| 问题 | 解决方案 |
|------|----------|
| 输入法漏字 | 设置`LC_CTYPE="en_US.UTF-8"`环境变量 |
| GTK应用启动缓慢 | 设置`GSK_RENDERER="gl"`环境变量 |
| Steam下载速度慢 | 禁用btrfs写时复制 |
| 屏幕分享异常 | 配置`XDG_CURRENT_DESKTOP=niri`环境变量 |

### 9.2 调试技巧

- 使用`journalctl`查看系统日志
- 使用`dmesg`查看内核消息
- 使用`niri --verbose`启动niri以查看详细日志
- 使用`waybar --log-level debug`启动waybar以查看详细日志

## 10. 总结

ShorinArchExperience项目是一个全面的Arch Linux配置和使用指南，包含了从系统安装到日常使用的各种配置和技巧。项目的核心价值在于：

1. **全面性**：涵盖了多种桌面环境和Wayland合成器的配置
2. **实用性**：提供了详细的安装和配置步骤
3. **个性化**：包含了丰富的主题和美化配置
4. **可扩展性**：模块化的配置结构便于用户根据自己的需求进行调整

通过本项目，用户可以快速上手Arch Linux系统，并根据自己的喜好进行个性化配置，打造一个美观、高效的Linux桌面环境。