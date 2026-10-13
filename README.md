[English](./English.md) | [中文](README.md)

![kcu logo](./Kcu_icon.png)
# KcuMigrator

“更好的迁移就在你的手中”-----项目发起者kongbai9288

本项目目前支持 FCL、Zalith、Pojav、Amethyst、HMCL-PE、澪-Ultimate 等大部分安卓Java edition启动器（正在努力适配T_T）

本项目使用AI生成代码，由人设计架构与实现方式并累计审核89次（数据至2026/10/14），如有不赞成，可以暂停使用本项目
* 注：有相当一部分代码实现使用了其他项目，如果你需要，请注意他们的相关政策，本项目不对其他项目的行为负责

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

### 启动器

- [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher) — 最早、最知名的 Android/iOS Java 版启动器，基于 Boardwalk。
- [ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2) — 基于 PojavLauncher 和 Jetpack Compose 重新设计的现代启动器。
- [FoldCraftLauncher (FCL)](https://github.com/FCL-Team/FoldCraftLauncher) — 功能丰富、更新活跃的 Android Java 版启动器，支持模组管理。
- [Amethyst-Android](https://github.com/AngelAuraMC/Amethyst-Android) — PojavLauncher 的官方继任项目。
- [HMCL-PE](https://github.com/HMCL-dev/HMCL-PE) — Hello Minecraft! Launcher 的 Android 移植版（已停止维护）。
- [MojoLauncher](https://github.com/MojoLauncher/MojoLauncher) — 基于 PojavLauncher 的启动器。
- [MCinaBox](https://github.com/AOF-Dev/MCinaBox) — 较早期的 Android Java 版启动器，封装了 BoatApp。
- [BoatApp](https://github.com/AOF-Dev/BoatApp) — 轻量级 Android Java 版启动环境。
- [ShardLauncher](https://github.com/ShardLauncher/ShardLauncher) — 基于 Jetpack Compose 的移动端启动器。
