[English](./English.md) | [中文](README.md)

![kcu logo](./Kcu_icon.png)
# KcuMigrator

“更好的迁移就在你的手中”-----项目发起者kongbai9288

本项目目前支持 FCL、Zalith、Pojav、Amethyst、HMCL-PE、澪-Ultimate 等大部分安卓Java edition启动器（正在努力适配T_T）

本项目使用AI生成代码，由人设计架构与实现方式并累计审核89次（数据至2026/10/14），如有不赞成，可以暂停使用本项目
* 注：有部分代码实现使用了其他项目/库，如果你需要，请注意他们的相关政策，本项目不对其他项目的行为负责

## 功能
1. 快速迁移相关文件，并把它们存放到对应位置（核心功能）
2. 支持地图编辑，世界编辑，数据包生成，服务器自动查找对应名称的模组并下载到本地（上传需要亲自确定，目前不提供自动上传功能）
3. 其他功能敬请期待

## 怎么用

1. 下载 Release 里的 <big>正式版 apk 安装
2. 打开 App
3. 到迁移页：选旧版本目录（里面有 `mods` 文件夹那个），选新版本目录，填目标 MC 版本和加载器，点扫描。
4. 勾选要迁移的东西，点开始迁移

## 隐私

代码里没凭据。没账号，有后端（仅为github oauth与curseforge api使用，并且可以替换），没统计，没广告。


- 如果对联网敏感，可以进入设置页面，关闭所有联网权限（尽量支持，如你发现我们出现了漏洞，欢迎提issue）

卸载 App 会删掉本机数据（工作目录等由您选定的运行部分和结果除外）。完整说明在 App 里：设置 → 关于 → 隐私说明。

## 第三方开源许可与致谢

本项目在开发过程中参考并使用了以下优秀的开源项目和第三方服务，在此向所有作者表示感谢！

### 核心依赖

| 项目名称 | 许可证 | 用途说明 |
| :--- | :--- | :--- |
| [AndroidX](https://developer.android.com/jetpack/androidx) | Apache 2.0 | 基础 UI 组件、生命周期管理与核心框架支持 |
| [WorkManager](https://developer.android.com/topic/libraries/architecture/workmanager) | Apache 2.0 | 后台定时检查更新、定时同步 |
| [Material Components](https://github.com/material-components/material-components-android) | Apache 2.0 | 界面控件、主题、对话框、底部导航 |
| [OkHttp](https://github.com/square/okhttp) | Apache 2.0 | 所有网络请求，多线程分块下载基础 |
| [Gson](https://github.com/google/gson) | Apache 2.0 | JSON 数据解析 |
| [Jsoup](https://github.com/jhy/jsoup) | MIT | 解析模组描述页面，提取下载链接 |
| [Coil](https://github.com/coil-kt/coil) | Apache 2.0 | 加载模组图标 |

### 翻译引擎
| 项目名称 | 许可证 | 用途说明 |
| :--- | :--- | :--- |
| [Google ML Kit Translate](https://developers.google.com/ml-kit/language/translation) | 非开源（受 Google APIs 条款约束） | 模组简介与网页的离线翻译（模型约 30MB，完全离线运行） |

> **关于 ML Kit 的特别说明**：ML Kit SDK 与翻译模型本身受《Google APIs 使用条款》约束，非可自由再分发的开源组件。已知限制：仅限手机/平板/笔记本/台式机使用；用于汽车、电视、家电等嵌入式设备需 Google 事先书面许可。

### 数据来源与 API
| 项目名称 | 说明 |
| :--- | :--- |
| [Modrinth](https://modrinth.com) | 通过公开 HTTP API 读取模组元数据（平台代码为 AGPL-3.0，本项目仅通过 API 读取数据，不构成代码衍生） |
| [CurseForge](https://www.curseforge.com) | 通过公开 API 与国内镜像 [MCIM](https://www.mcimirror.top) 读取模组元数据 |
| [Pterodactyl](https://pterodactyl.io) | 客户端调用其 Client API（面板服务端为 MIT 许可） |
| [GitHub REST API](https://docs.github.com/en/rest) | 用于读取 release 与仓库文件，遵循 GitHub 服务条款 |

### 参考实现（仅参考思路，未直接依赖代码）
| 项目名称 | 许可证 | 参考点 |
| :--- | :--- | :--- |
| [lingochamp/FileDownloader](https://github.com/lingochamp/FileDownloader) | Apache 2.0 | 多任务并发、断点续传、分块下载调度思路（本项目按同样思路用 OkHttp 自行实现） |
| [jackfengji/android-download-manager](https://github.com/jackfengji/android-download-manager) | MIT | HTTP Range 分块下载、并发任务数控制 |
| [SirLYC/YC-Downloader](https://github.com/SirLYC/YC-Downloader) | MIT | 多任务队列、速度限制、进度回调节流 |
| [Blocktopograph](https://github.com/MithrilMania/Blocktopograph) | GPL-3.0 | 参考了其使用逻辑

### NBT 读写与数据包生成器
| 项目名称 | 许可证 | 用途说明 |
| :--- | :--- | :--- |
| [ViaNBT](https://github.com/ViaVersion/ViaNBT) | MIT | 读写 `level.dat` 等 NBT 格式文件 |
| [misode.github.io](https://github.com/misode/misode.github.io) | MIT | 数据包与资源包生成器（内置 137 个生成器，离线可用） |
| [misode-vianbt-android](https://github.com/kongbai9288/misode-vianbt-android) | MIT | 上述项目的 Android 适配版（替换 fastutil 依赖、移动端布局、离线打包） |

### 系统组件
- **Android Download Manager** (`android.app.DownloadManager`)：用于应用更新下载，断点续传与安装调起由系统提供。
- **AndroidX Core / FileProvider** (Apache 2.0)：用于崩溃日志通过系统分享面板发送给其他应用。
- **Material Icons** ([fonts.google.com/icons](https://fonts.google.com/icons)) (Apache 2.0)：本项目所有图标资源。

---

**说明：**
- 本项目自身代码未使用任何 copyleft（GPL/AGPL/LGPL）组件。
- 如您发现本项目使用了未在此列出的第三方代码，或认为存在许可冲突，欢迎提交 Issue。
- 此列表随版本更新，以应用内最新版本为准。。

## 测试版

[KCU测试版](https://github.com/kongbai9288/mc-mod-migrator)
- ⚠️注意：这可能会使你的运行出现严重错误，非测试人员请勿使用本版本（如你使用了此版本，造成的失误将自行承担）

## 项目历史

本项目于2026年9月24日建立，已有89个版本，因不稳定与品牌形象升级于2026年10月14日迁移至本仓库，原仓库承担构建与测试版的任务

## 友情链接

## 安卓 Java 版启动器

### 活跃维护 / 主流推荐

| 启动器名称 | 地址 | 核心说明 |
|---|---|---|
| **PojavLauncher** | [https://github.com/PojavLauncherTeam/PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher) | 所有安卓 Java 版启动器的“老祖宗”，基于 Boardwalk 开发。现已由 Amethyst-Android 接替。 |
| **Amethyst-Android** | [https://github.com/AngelAuraMC/Amethyst-Android](https://github.com/AngelAuraMC/Amethyst-Android) | PojavLauncher 的官方继任项目，支持几乎所有 Java 版版本（从 rd-132211 到最新快照）。 |
| **FoldCraftLauncher (FCL)** | [https://github.com/FCL-Team/FoldCraftLauncher](https://github.com/FCL-Team/FoldCraftLauncher) | 基于 HMCL 核心功能 + PojavLauncher/Amethyst 后端，支持全模组加载器，内置多版本 Java 运行时。GPL-3.0。 |
| **ZalithLauncher 2 (ZL2)** | [https://github.com/ZalithLauncher/ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2) | 基于 PojavLauncher 核心 + Jetpack Compose + Material Design 3，现代化 UI，当前社区最活跃的启动器之一。GPL-3.0。 |
| **MojoLauncher / MJLauncher** | [https://github.com/MojoLauncher/MojoLauncher](https://github.com/MojoLauncher/MojoLauncher) | 基于 PojavLauncher 的衍生项目。注意：MJLauncher 是 MojoLauncher 更名后的版本，两者为同一项目。 |
| **ShardLauncher** | [https://github.com/ShardLauncher/ShardLauncher](https://github.com/ShardLauncher/ShardLauncher) | 基于 Jetpack Compose 的移动端启动器，☆127，规模较小但仍在更新。 |
| **TurtleLauncher** | [https://github.com/Endiq-jar/TurtleLauncher](https://github.com/Endiq-jar/TurtleLauncher) | 基于 Boardwalk 的现代化启动器，Material 3 设计，支持 Fabric/Quilt/Forge/NeoForge，GPL-3.0 开源。 |
| **DroidBridge Launcher** | [https://play.google.com/store/search?q=DroidBridge%20Launcher](https://play.google.com/store/search?q=DroidBridge%20Launcher) | 独立安卓启动器框架，面向正版 Java 版用户，支持手机/平板/掌机/手柄/键鼠等多种输入设备。 |
| **澪-Ultimate (Mio Launcher Ultimate)** | 该版本没有独立仓库，请使用bilibili搜索下载 | 使用 Boat 内核，启动速度快，控制器（按键布局）设计较好。 |
| **Pojav Zenith Horizon (PZH)** | [https://github.com/MCSP-Site/PojavZenithHorizon](https://github.com/MCSP-Site/PojavZenithHorizon) | 由墨北MovTery基于 PojavLauncher 深度魔改，是其后续项目 ZalithLauncher 的前身。 |
| **SolCraftLauncher** | [https://github.com/SCL-ARCHIVE/SolCraftLauncher](https://github.com/SCL-ARCHIVE/SolCraftLauncher) | PojavLauncher/Amethyst 的 Fork，增加了更多技术特性、新渲染器和 QOL 改进。 |
| **XDAetherium** | [https://github.com/Promastergame/XDAetherium](https://github.com/Promastergame/XDAetherium) | 基于 Amethyst/PojavLauncher 的 Fork，支持 Ely.by 账户和离线账户，优化了 ARM 设备性能。 |
| **Log4Java** | [https://www.rustore.ru/](https://www.rustore.ru/)（RuStore 搜索 Log4Java） | 基于 MojoLauncher 的启动器，支持所有 Minecraft 版本及 Forge/Fabric 等模组加载器。 |
| **CRAZElauncher** | [https://github.com/Mehetab1234/CRAZElauncher](https://github.com/Mehetab1234/CRAZElauncher) | Zalith Launcher 的社区重制版本，致力于优化用户体验、降低游玩门槛。 |
| **Titan Launcher** | [https://play.google.com/store/search?q=Titan%20Launcher%20Minecraft](https://play.google.com/store/search?q=Titan%20Launcher%20Minecraft) | 一款在 Google Play 上架的 Minecraft Java 版启动器，提供免费下载。 |
| **DuckCraft Launcher** | [https://uyen11a1-star.github.io](https://uyen11a1-star.github.io) | 基于 MojoLauncher/PojavLauncher 稳定引擎，支持全版本、Forge/Fabric 模组，内置模组浏览器。 |
| **Dawnland Launcher** | NexusMC 社区发布（可于 [https://nexusmc.org](https://nexusmc.org) 搜索） | 极速、轻量、跨平台的现代 Minecraft 启动器，支持多实例与模组管理。 |
| **PojavLauncherPlus** | [https://github.com/L10NDev/PojavLauncherPlus](https://github.com/L10NDev/PojavLauncherPlus) | 基于原版 PojavLauncher 的功能拓展优化版，支持自定义版本隔离、Mod 管理、直连服务器等。 |
| **Su** | [https://github.com/carrot12327/Su](https://github.com/carrot12327/Su) | 基于 PojavLauncher 的启动器，支持从 rd-132211 到最新快照的几乎所有版本。 |
| **Pojav-Glow-Worm** | [https://github.com/Vera-Firefly/Pojav-Glow-Worm](https://github.com/Vera-Firefly/Pojav-Glow-Worm) | PojavLauncher 的修改版，增加了更多实用功能。非官方版本。 |
| **Pojav-Mobileglues** | [https://github.com/coder-fast/Pojav-Mobileglues](https://github.com/coder-fast/Pojav-Mobileglues) | PojavLauncher 的修改版，集成了 MobileGlues 渲染器，旨在提升兼容性与性能。非官方版本。 |

### 已停止维护 / 归档参考

| 启动器名称 | 地址 | 状态说明 |
|---|---|---|
| **ZalithLauncher (一代)** | [https://github.com/ZalithLauncher/ZalithLauncher](https://github.com/ZalithLauncher/ZalithLauncher) | ZL2 的前身项目，已归档，由 ZL2 接替。 |
| **HMCL-PE** | [https://github.com/HMCL-dev/HMCL-PE](https://github.com/HMCL-dev/HMCL-PE) | Hello Minecraft! Launcher 的 Android 移植版，已停止维护。官方推荐使用 FCL 或 PojavLauncher。 |
| **HMCL-PE-Zink** | [https://github.com/Vera-Firefly/HMCL-PE-Zink](https://github.com/Vera-Firefly/HMCL-PE-Zink) | HMCL-PE 社区分支，尝试整合 Zink 渲染器，已停止。 |
| **MCinaBox** | [https://github.com/AOF-Dev/MCinaBox](https://github.com/AOF-Dev/MCinaBox) | 早期安卓 Java 版启动器，封装了 BoatApp，已停止更新。 |
| **BoatApp** | [https://github.com/AOF-Dev/Boat](https://github.com/AOF-Dev/Boat) | 轻量级 Android Java 版运行环境，是 MCinaBox、澪-Ultimate 等项目的底层依赖。已归档。 |
| **Boardwalk** | [https://github.com/zhuowei/Boardwalk](https://github.com/zhuowei/Boardwalk) | PojavLauncher 的底层项目，已不再活跃开发。 |
| **TofuCraftLauncher** | [https://github.com/Redstone2337/TofuCraftLauncher](https://github.com/Redstone2337/TofuCraftLauncher) | 基于 FCL 的 fork，社区维护，活跃度较低。 |
| **PojavLauncher-ltw-quick-settings** | [https://github.com/TransBluelight/PojavLauncher-ltw-quick-settings](https://github.com/TransBluelight/PojavLauncher-ltw-quick-settings) | PojavLauncher 的 LTW 渲染器快速设置分支，已归档。 |
| **PojavLauncher-Beta-Zink** | [https://github.com/ogdsjfg/PojavLauncher-Beta-Zink](https://github.com/ogdsjfg/PojavLauncher-Beta-Zink) | PojavLauncher 的 Beta 分支，专注于 Zink 渲染器优化，已停止更新。 |

### 渲染器（核心翻译层）

| 渲染器名称 | 地址 | 核心说明 |
|---|---|---|
| **Holy GL4ES** | [https://github.com/AngelAuraMC/HolyGL4ES](https://github.com/AngelAuraMC/HolyGL4ES) | PojavLauncher 的默认渲染器，专为性能优化，支持 OpenGL 2.1，兼容所有版本，适合 1.16.5 及更早版本[reference:0]。 |
| **MobileGlues (MG)** | [https://github.com/MobileGL-Dev/MobileGlues-release](https://github.com/MobileGL-Dev/MobileGlues-release) | 现代全能之选，基于 OpenGL ES 3.2，性能卓越，完美支持 Sodium、Iris 光影及大型模组，推荐用于 1.17+ 版本[reference:1]。 |
| **Zink (Vulkan Zink)** | [https://gitlab.freedesktop.org/mesa/mesa/-/tree/main/src/gallium/drivers/zink](https://gitlab.freedesktop.org/mesa/mesa/-/tree/main/src/gallium/drivers/zink) | 基于 Vulkan 的 OpenGL 转换层，模组与光影兼容性极强，但性能较低，更适合 Adreno GPU（骁龙）设备[reference:2]。 |
| **ANGLE** | [https://github.com/google/angle](https://github.com/google/angle) | 运行在 Vulkan 上，支持 OpenGL 3.2，仅适用于 1.17+ 版本。在 iOS 上性能优于 Holy GL4ES，但在 Android 上已被 LTW 取代[reference:3]。 |
| **LTW (Large Thin Wrapper)** | [https://github.com/MojoLauncher/LTW](https://github.com/MojoLauncher/LTW) | 专为 PojavLauncher 优化的实验性渲染器，针对新版 Minecraft 特别适配，能直接运行 Sodium 等优化模组[reference:4]。 |
| **VirGL** | [https://virglrenderer.pages.freedesktop.org/](https://virglrenderer.pages.freedesktop.org/) | 通过虚拟 GPU 实现硬件加速的 OpenGL，在支持的设备上性能较好。FCL 内置支持[reference:5]。 |
| **NG-GL4ES / Krypton Wrapper** | [https://github.com/BZLZHH/NG-GL4ES](https://github.com/BZLZHH/NG-GL4ES) | GL4ES 的现代化 Fork，支持更高级的着色器，可运行几乎所有版本的 Minecraft，效率与 GL4ES 相近[reference:6]。 |
| **Open4ES** | [https://github.com/AnikyMX/Open4ES-Shader-Android](https://github.com/AnikyMX/Open4ES-Shader-Android) | 基于 GL4ES 的光影项目，将 SEUS 等著名光影转换为可在安卓 Java 版上运行，兼容 Adreno、Mali 和 PowerVR GPU[reference:7]。 |

### 渲染器（驱动与虚拟化）

| 渲染器名称 | 地址 | 核心说明 |
|---|---|---|
| **Freedreno** | [https://gitlab.freedesktop.org/mesa/mesa/-/tree/main/src/gallium/drivers/freedreno](https://gitlab.freedesktop.org/mesa/mesa/-/tree/main/src/gallium/drivers/freedreno) | 针对高通 Adreno GPU 的 Mesa 驱动，可开启部分光影，但性能极低，仅适用于非常老旧的骁龙设备[reference:8]。 |
| **VGPU** | 已集成至 Holy GL4ES | 虚拟 GPU 实现，曾作为独立渲染器，现已集成至 Holy GL4ES 中，不再单独提供[reference:9]。 |

### 渲染器（Mod / 替代方案）

| 名称 | 地址 | 核心说明 |
|---|---|---|
| **VulkanMod** | [https://github.com/shindozk/VulkanMod-Android-ARM64](https://github.com/shindozk/VulkanMod-Android-ARM64) | 将 Minecraft 的 OpenGL 渲染器替换为 Vulkan 的 Mod，专为 ARM64 安卓设备优化，适用于 Zalith Launcher 和 PojavLauncher。 |

### 相关工具

| 名称 | 地址 | 说明 |
|---|---|---|
| **FCL 第三方下载站** | [https://github.com/XiaoluoFoxington/FCL.website.NEXT](https://github.com/XiaoluoFoxington/FCL.website.NEXT) | 社区自发搭建的 FCL 非官方下载站，提供 FCL、ZL 及渲染器、驱动、Java 等资源。 |
| **EnchantNet** | [https://github.com/FCL-Team/EnchantNet](https://github.com/FCL-Team/EnchantNet) | FCL 团队的远程连接工具，用于 Minecraft: Java Edition。 |
| **OpenJDK-Builder** | [https://github.com/aaaapai/OpenJDK-Builder](https://github.com/aaaapai/OpenJDK-Builder) | 为安卓启动器提供 Java 运行环境的构建工具。 |
