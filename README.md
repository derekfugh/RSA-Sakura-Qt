# RSA-Sakura-Qt (Linux GUI)

Linux 版 Qt6 UI for RSA-Sakura。本应用提供了与 macOS 版完全一致的核心加密/解密、密钥管理和授权拖拽体验。底层加密引擎及具体功能说明，请参阅 [RSA-Sakura-Driver (macOS 版)](https://github.com/derekfugh/RSA-Sakura-Driver)。

Linux version of the Qt6 GUI for RSA-Sakura. It provides the same core encryption/decryption, key management, and drag-and-drop experience as the macOS version. For the underlying crypto engine and detailed documentation, please refer to the [macOS version](https://github.com/derekfugh/RSA-Sakura-Driver).

## ✨ 功能特性 (Features)

*   **完全对标的 UI 体验**：支持拖拽加解密、多页面状态同步、复选框状态记忆、多核/多线程加速。
*   **暗黑模式适配**：精致的界面布局。
*   **单实例运行**：多次启动会自动将已有窗口调至前台。
*   **X11/Wayland 兼容**：基于 Qt6 构建。

## 🛠️ 安装与依赖 (Prerequisites & Installation)

**1. 安装运行依赖**
本项目基于 Qt6。在运行或编译前，请确保系统已安装 Qt6 运行库。：

Debian / Ubuntu:
```bash
sudo apt update
sudo apt install libqt6widgets6 libqt6network6 libxcb-cursor0 libxkbcommon-x11-0 libxcb-icccm4 libxcb-keysyms1 libxcb-image0
```
或前往 Releases 页面下载最新的压缩包并解压。在终端里，执行 release 中的 ‘run-debug.sh’，该工具将自动安装Qt库，并尝试启动 Driver 程序。如启动失败，将在终端里输出缺失的库的信息。

(注：如果是 Fedora / Arch 等发行版，请安装对应的 qt6-base、xcb 等库。由于不同发行版包名差异，若遇到缺失库报错，请使用 ldd ./RSA-Sakura-Qt | grep "not found" 排查并安装对应包。)

2. 安装 Driver

安装快捷方式（加到系统应用列表）
./install_driver_linux.sh

卸载快捷方式（如需清理）
./install_driver_linux.sh -u

⚠️ 重要提醒 (Important Notes)
底层核心组件依赖：本 App 仅作为图形界面外壳。使用前，请务必确保已正确安装 RSA-Sakura 的命令行核心组件（如 xrsaoapp.sw、sigd、sige 等），并在 /usr/bin 或 /usr/local/bin 下配置好了对应的软链接。

关于多核模式 (Multi-core Mode)：开启多核模式会极大程度榨干 CPU 性能以加速处理。该模式专为单任务大批量处理设计。请勿在多个终端窗口中同时开启多核模式处理大批量数据，以避免触发 Linux 底层信号量资源耗尽（资源竞争）导致的系统卡死。

📄 开源协议 (License)
本项目遵循与 Mac 版相同的开源协议。
