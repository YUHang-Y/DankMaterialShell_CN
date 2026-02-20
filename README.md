


<div align="center">
  <a href="https://danklinux.com">
    <img src="assets/danklogo.svg" alt="DankMaterialShell" width="200">
  </a>

### 一款现代化的 Wayland 桌面外壳

基于 [Quickshell](https://quickshell.org/) 和 [Go](https://go.dev/) 构建

[![Documentation](https://img.shields.io/badge/docs-danklinux.com-9ccbfb?style=for-the-badge&labelColor=101418)](https://danklinux.com/docs)
[![GitHub stars](https://img.shields.io/github/stars/AvengeMedia/DankMaterialShell?style=for-the-badge&labelColor=101418&color=ffd700)](https://github.com/AvengeMedia/DankMaterialShell/stargazers)
[![GitHub License](https://img.shields.io/github/license/AvengeMedia/DankMaterialShell?style=for-the-badge&labelColor=101418&color=b9c8da)](https://github.com/AvengeMedia/DankMaterialShell/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/v/release/AvengeMedia/DankMaterialShell?style=for-the-badge&labelColor=101418&color=9ccbfb)](https://github.com/AvengeMedia/DankMaterialShell/releases)
[![AUR version](https://img.shields.io/aur/version/dms-shell-bin?style=for-the-badge&labelColor=101418&color=9ccbfb)](https://aur.archlinux.org/packages/dms-shell-bin)
[![AUR version (git)](<https://img.shields.io/aur/version/dms-shell-git?style=for-the-badge&labelColor=101418&color=9ccbfb&label=AUR%20(git)>)](https://aur.archlinux.org/packages/dms-shell-git)
[![Ko-Fi donate](https://img.shields.io/badge/donate-kofi?style=for-the-badge&logo=ko-fi&logoColor=ffffff&label=ko-fi&labelColor=101418&color=f16061&link=https%3A%2F%2Fko-fi.com%2Fdanklinux)](https://ko-fi.com/danklinux)

</div>

DankMaterialShell 是一个为 [niri](https://github.com/YaLTeR/niri)、[Hyprland](https://hyprland.org/)、[MangoWC](https://github.com/DreamMaoMao/mangowc)、[Sway](https://swaywm.org)、[labwc](https://labwc.github.io/)、[Scroll](https://github.com/dawsers/scroll)、[Miracle WM](https://github.com/miracle-wm-org/miracle-wm) 以及其他 Wayland 合成器打造的完整桌面外壳。它将 waybar、swaylock、swayidle、mako、fuzzel、polkit 以及您通常需要拼凑起来以构建桌面环境的所有其他组件集于一身。

## 仓库结构

这是一个包含外壳界面和核心后端服务的单体仓库：

```
DankMaterialShell/
├── quickshell/         # 基于 QML 的外壳界面
│   ├── Modules/        # UI 组件（面板、小部件、覆盖层）
│   ├── Services/       # 系统集成（音频、网络、蓝牙）
│   ├── Widgets/        # 可复用的 UI 控件
│   └── Common/         # 共享资源和主题
├── core/               # Go 后端和 CLI
│   ├── cmd/            # dms CLI 和 dankinstall 二进制文件
│   ├── internal/       # 系统集成、IPC、发行版支持
│   └── pkg/            # 共享包
├── distro/             # 发行版打包
│   ├── fedora/         # Fedora RPM 规范
│   ├── debian/         # Debian 打包
│   └── nix/            # NixOS/home-manager 模块
└── flake.nix           # 用于声明式安装的 Nix flake
```

## 效果预览

<div align="center">

https://github.com/user-attachments/assets/1200a739-7770-4601-8b85-695ca527819a

</div>

<details><summary><strong>更多截图</strong></summary>

<div align="center">

<img src="https://github.com/user-attachments/assets/203a9678-c3b7-4720-bb97-853a511ac5c8" width="600" alt="桌面" />

<img src="https://github.com/user-attachments/assets/a937cf35-a43b-4558-8c39-5694ff5fcac4" width="600" alt="仪表盘" />

<img src="https://github.com/user-attachments/assets/2da00ea1-8921-4473-a2a9-44a44535a822" width="450" alt="启动器" />

<img src="https://github.com/user-attachments/assets/732c30de-5f4a-4a2b-a995-c8ab656cecd5" width="600" alt="控制中心" />

</div>

</details>

## 安装

```bash
curl -fsSL https://install.danklinux.com | sh
```

一条命令即可在 Arch、Fedora、Debian、Ubuntu、openSUSE 或 Gentoo 上安装 DMS 及其所有依赖。

**[手动安装指南](https://danklinux.com/docs/dankmaterialshell/installation)**

## 功能特性

**动态主题**
基于壁纸的颜色方案，可使用 [matugen](https://github.com/InioX/matugen) 和 dank16 自动为 GTK、Qt、终端、编辑器（vscode, vscodium）等应用设置主题。

**系统监控**
通过 [dgop](https://github.com/AvengeMedia/dgop) 实时监控 CPU、内存、GPU 指标和温度。提供进程列表，支持搜索和管理。

**强大的启动器**
Spotlight 风格的搜索功能，可搜索应用程序、文件（[dsearch](https://github.com/AvengeMedia/danksearch)）、表情符号、正在运行的窗口，并支持计算器和命令执行。可通过插件扩展。

**控制中心**
统一的界面，用于管理网络、蓝牙、音频设备、显示设置和夜间模式。

**智能通知**
通知中心，支持消息分组、富文本显示和键盘导航。

**媒体集成**
支持 MPRIS 播放器控制、日历同步、天气小部件以及带图片预览的剪贴板历史。

**会话管理**
提供锁屏、空闲检测、根据电源/电池状态自动锁定/挂起功能，并支持登录管理器。

**插件系统**
通过[插件注册表](https://plugins.danklinux.com)扩展功能。

## 支持的合成器

与 [niri](https://github.com/YaLTeR/niri)、[Hyprland](https://hyprland.org/)、[Sway](https://swaywm.org/)、[MangoWC](https://github.com/DreamMaoMao/mangowc)、[labwc](https://labwc.github.io/)、[Scroll](https://github.com/dawsers/scroll) 和 [Miracle WM](https://github.com/miracle-wm-org/miracle-wm) 配合最佳，可完整支持工作区切换、概览集成和显示器管理。在其他 Wayland 合成器上，部分功能可能受限。

[合成器配置指南](https://danklinux.com/docs/dankmaterialshell/compositors)

## 命令行界面

通过命令行或按键绑定控制外壳：

```bash
dms run              # 启动外壳
dms ipc call spotlight toggle
dms ipc call audio setvolume 50
dms ipc call wallpaper set /path/to/image.jpg
dms brightness list  # 列出可用显示器
dms plugins search   # 浏览插件注册表
```

[完整的 CLI 和 IPC 文档](https://danklinux.com/docs/dankmaterialshell/keybinds-ipc)

## 文档

- **网站:** [danklinux.com](https://danklinux.com)
- **文档:** [danklinux.com/docs](https://danklinux.com/docs/)
- **主题:** [应用程序主题](https://danklinux.com/docs/dankmaterialshell/application-themes) | [自定义主题](https://danklinux.com/docs/dankmaterialshell/custom-themes)
- **插件:** [开发指南](https://danklinux.com/docs/dankmaterialshell/plugins-overview)
- **支持:** [Ko-fi](https://ko-fi.com/avengemediallc)

## 开发

请参阅各组件的详细文档：

- **[quickshell/](quickshell/)** - QML 外壳开发、小部件和模块
- **[core/](core/)** - Go 后端、CLI 工具和系统集成
- **[distro/](distro/)** - 发行版打包（Fedora、Debian、NixOS）

### 从源码构建

**核心 + Dankinstall:**

```bash
cd core
make              # 构建 dms CLI
make dankinstall  # 构建安装器
```

**外壳:**

```bash
quickshell -p quickshell/
```

**NixOS:**

```nix
{
  inputs.dms.url = "github:AvengeMedia/DankMaterialShell";

  # 在 home-manager 或 NixOS 配置中使用
  imports = [ inputs.dms.homeModules.dank-material-shell ];
}
```

## 贡献

欢迎各种形式的贡献。修复 Bug、添加小部件、实现新功能、完善文档或开发插件，都将使项目变得更好。

1. Fork 本仓库
2. 进行您的修改
3. 充分测试
4. 提交 Pull Request

如需贡献文档，请参阅 [DankLinux-Docs](https://github.com/AvengeMedia/DankLinux-Docs)。

## 致谢

- [quickshell](https://quickshell.org/) - 外壳框架
- [niri](https://github.com/YaLTeR/niri) - 滚动式窗口管理器
- [Ly-sec](http://github.com/ly-sec) - 源自 [Noctalia](https://github.com/noctalia-dev/noctalia-shell) 的壁纸特效
- [soramanew](https://github.com/soramanew) - 灵感源自 [Caelestia](https://github.com/caelestia-dots/shell)
- [end-4](https://github.com/end-4) - 灵感源自 [dots-hyprland](https://github.com/end-4/dots-hyprland)

## Star 历史

[![Star History Chart](https://api.star-history.com/svg?repos=AvengeMedia/DankMaterialShell&type=date&legend=top-left)](https://www.star-history.com/#AvengeMedia/DankMaterialShell&type=date&legend=top-left)

## 许可证

MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。
```
