# DarlingOS 项目归档

> 整理日期：2026-10-29
> 基于 Arch Linux 打造的定制操作系统

---

## 一、系统基础

| 项目 | 说明 |
|------|------|
| 基础系统 | Arch Linux |
| 内核 | linux (默认) / linux-zen (备选) |
| 启动方式 | UEFI + systemd-boot |
| 显示服务器 | Wayland |
| Shell | Hyprland (平铺式 Wayland 合成器) |

---

## 二、桌面环境

### 2.1 Hyprland
- **类型**：Wayland 平铺式窗口管理器
- **特点**：动画效果丰富、高度可定制、GPU 加速
- **配置目录**：`~/.config/hypr/`

### 2.2 Quickshell
- **类型**：QML 桌面外壳框架
- **说明**：DMS 基于 Quickshell 构建

### 2.3 DMS (DankMaterialShell)
- **类型**：基于 Quickshell 的桌面环境
- **特点**：Material Design 风格、集成 DMS 桌面环境
- **功能**：任务栏、启动器、系统托盘、窗口管理、控制中心

---

## 三、已安装软件清单

### 3.1 系统工具
| 软件 | 说明 | 安装方式 |
|------|------|----------|
| Paru | AUR 助手 | pacman |
| Git | 版本控制 | pacman |
| Python 3 | 编程语言 | pacman |
| Node.js | JavaScript 运行时 | pacman |

### 3.2 虚拟化
| 软件 | 说明 | 安装方式 |
|------|------|----------|
| QEMU | 虚拟机模拟器 | pacman |
| KVM | 内核虚拟化模块 | pacman |
| virt-manager | 图形化虚拟机管理 | pacman |
| libvirt | 虚拟化库 | pacman |

### 3.3 Windows 兼容层
| 软件 | 说明 | 安装方式 |
|------|------|----------|
| deep-wine-runner | Wine 运行器（国产） | AUR/paru |
| Wine | Windows 兼容层 | pacman |

### 3.4 Android 兼容
| 软件 | 说明 | 状态 |
|------|------|------|
| Waydroid | LXC 容器运行 Android | 已删除（不支持 NVIDIA） |
| binder_linux | Android 内核模块 | 已安装 (DKMS) |
| libhoudini | ARM 转译（Intel CPU） | 已配置 |

### 3.5 网络工具
| 软件 | 说明 | 安装方式 |
|------|------|----------|
| Cloudflare Warp | 网络加速 | deb 解包安装 |
| ChmlFrp | 内网穿透 | 手动安装 |
| bore | 轻量级隧道 | 手动安装 |

### 3.6 开发工具
| 软件 | 说明 |
|------|------|
| VS Code | 代码编辑器 |
| Neovim | 终端编辑器 |
| Docker | 容器引擎 |

### 3.7 输入法
| 软件 | 说明 |
|------|------|
| Fcitx5 | 输入法框架 |
| 中文输入法 | 已配置自启动 |

### 3.8 截图与工具
| 软件 | 说明 |
|------|------|
| grim | Wayland 截图工具 |
| slurp | 选区工具 |
| hyprshot | Hyprland 截图脚本 |

---

## 四、内核模块

| 模块 | 说明 | 状态 |
|------|------|------|
| binder_linux | Android Binder IPC | 已安装 (DKMS) |
| ashmem | Android 共享内存 | 内置内核 |
| NVIDIA 驱动 | NVIDIA 显卡驱动 | 已编译 (DKMS) |
| bcachefs | 文件系统 | 已安装 |

---

## 五、项目仓库

| 项目 | 地址 | 说明 |
|------|------|------|
| Darling-Android | https://github.com/DarlingZeroTwo-Cloud/Darling-Android | chroot 方式运行 Android 应用（已归档） |
| Darling-Cloud | GitHub | VNT 组网客户端 |
| darling-cloud-server-v1 | GitHub | 服务端 |
| Darling-Cloud-WebView | GitHub | WebView 套壳 |
| Darling-Cloud-Fusion | GitHub | 融合版（Go + Flutter） |

---

## 六、系统配置

### 6.1 磁盘布局
| 分区 | 大小 | 挂载点 | 说明 |
|------|------|--------|------|
| sda1 | 1G | /boot/EFI | EFI 系统分区 |
| sda2 | 46G | / | 根目录 |
| sda3 | 415G | /home | 用户数据 |

### 6.2 符号链接优化
- `/var/cache/pacman` → `/home/darling/root_data/cache/pacman`
- `/opt` → `/home/darling/root_data/opt`
- `/var/lib/apm` → `/home/darling/root_data/apm`

---

## 七、硬件信息

| 项目 | 说明 |
|------|------|
| CPU | Intel i3-4170 |
| 内存 | 8GB |
| 显卡 | Intel HD 4400 核显 |
| 主板 | H81 |
| 显示器 | 1920×1080 |

---

## 八、已知问题

1. **系统偶发卡死**：可能与符号链接、Zen 内核或驱动有关
2. **SSH 连接不稳定**：frp/bore 隧道时断时续
3. **Waydroid 不兼容**：NVIDIA 闭源驱动不支持
4. **Cloudflare Warp GUI**：Wayland 下无法显示窗口

---

## 九、后续计划

- [ ] 排查系统卡死原因
- [ ] 优化 Hyprland 配置
- [ ] 完善 DMS 桌面环境
- [ ] 选择新的 Android 兼容方案
- [ ] 系统备份与恢复方案

---

**归档人**：Darling OS 项目组
**版本**：v1.0
