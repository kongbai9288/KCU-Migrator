![kcu logo](./IMG_20261013_005127.png)
# ModMigrator

安卓上的 Minecraft Java 版模组迁移工具。

“更好的迁移就在你的手中”-----项目发起者kongbai9288

支持 FCL、Zalith、Pojav、Amethyst、HMCL-PE、澪-Ultimate 等大部分安卓启动器（正在努力适配T_T）

本项目使用AI生成代码，由人设计架构与实现方式，如有不赞成，可以暂停使用本项目
* 注：有相当一部分代码实现使用了其他项目，如果你需要，请注意他们的相关政策，本项目不对其他项目的行为负责

## 为什么写这个

Minecraft 大版本一更新，旧模组基本全废。你得先看旧版本装了啥，再去 Modrinth / CurseForge 找新版，还得注意加载器对不对——Forge 的模组新版可能只出 NeoForge。模组装得少还行，装三四十个就很容易漏。

这工具就是把扫描、比对、复制这几步自动做了。

## 功能

- **迁移**：选旧目录和新目录，扫描后给方案。用 SHA-1 识别模组，不靠文件名猜。自动查目标版本有没有兼容版。勾选后一键复制。
- **模组管理**：读 jar 信息，显示图标、版本、作者。能启用 / 禁用 / 删除（有回收站）。能分析依赖，给安装顺序。
- **整合包**：导出 `.mrpack`，导入 `.mrpack` 后可以做更新检查。只有主动导入并登记的整合包才会检查更新。
- **其他**：跨设备同步（用你自己的 GitHub 仓库）、服务器面板更新检测、离线翻译、Modrinth / CurseForge 搜索下载。

## 怎么用

1. 下载 Release 里的 apk 安装。
2. 打开 App，设置 → 存储，选个工作目录（导出包、缓存、备份都放这）。
3. 到迁移页：选旧版本目录（里面有 `mods` 文件夹那个），选新版本目录，填目标 MC 版本和加载器，点扫描。
4. 勾选要迁移的东西，点开始迁移。

第一次用会有引导，跟着走就行。

## 隐私

代码里没凭据。没账号，没自建服务器，没统计，没广告。

联网的地方就几个：

- 搜模组 / 查版本：给 Modrinth 发搜索词、MC 版本、加载器。
- 按文件识别模组：发文件的 SHA-1，不是文件名也不是路径。
- GitHub 登录：读写你自己的仓库，不存密码和 OAuth Secret。
- 翻译：发模组简介文本，开离线模式就不发。

卸载 App 会删掉本机数据（你自己导出的文件除外）。完整说明在 App 里：设置 → 关于 → 隐私说明。

## 许可

MIT。第三方库许可见 `NOTICES.md` 或 App 内设置 → 关于 → 第三方开源许可。

Minecraft 是 Mojang Studios 的商标。这工具不是官方的，不含游戏本体、资源或受版权保护的素材。

## 测试版

[KCU测试版](https://github.com/kongbai9288/mc-mod-migrator)

## 启动器

- [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher) — 最早、最知名的 Android/iOS Java 版启动器，基于 Boardwalk。
- [ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2) — 基于 PojavLauncher 和 Jetpack Compose 重新设计的现代启动器。
- [FoldCraftLauncher (FCL)](https://github.com/FCL-Team/FoldCraftLauncher) — 功能丰富、更新活跃的 Android Java 版启动器，支持模组管理。
- [Amethyst-Android](https://github.com/AngelAuraMC/Amethyst-Android) — PojavLauncher 的官方继任项目。
- [HMCL-PE](https://github.com/HMCL-dev/HMCL-PE) — Hello Minecraft! Launcher 的 Android 移植版（已停止维护）。
- [MojoLauncher](https://github.com/MojoLauncher/MojoLauncher) — 基于 PojavLauncher 的启动器。
- [MCinaBox](https://github.com/AOF-Dev/MCinaBox) — 较早期的 Android Java 版启动器，封装了 BoatApp。
- [BoatApp](https://github.com/AOF-Dev/BoatApp) — 轻量级 Android Java 版启动环境。
- [ShardLauncher](https://github.com/ShardLauncher/ShardLauncher) — 基于 Jetpack Compose 的移动端启动器。
