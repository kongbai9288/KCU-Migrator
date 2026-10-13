![kcu logo](./IMG_20261013_005127.png)
# ModMigrator

“更好的迁移就在你的手中”-----项目发起者kongbai9288

本项目目前支持 FCL、Zalith、Pojav、Amethyst、HMCL-PE、澪-Ultimate 等大部分安卓启动器（正在努力适配T_T）

本项目使用AI生成代码，由人设计架构与实现方式，如有不赞成，可以暂停使用本项目
* 注：有相当一部分代码实现使用了其他项目，如果你需要，请注意他们的相关政策，本项目不对其他项目的行为负责

## 功能
1.快速迁移相关文件，并把它们存放到对应位置（核心功能）
2.支持地图编辑，世界编辑，数据包生成，服务器自动查找对应名称的模组并下载到本地（上传需要亲自确定，目前不提供自动上传功能）
3.其他功能敬请期待

## 怎么用

1. 下载 Release 里的 <big>正式版 apk 安装
2. 打开 App
3. 到迁移页：选旧版本目录（里面有 `mods` 文件夹那个），选新版本目录，填目标 MC 版本和加载器，点扫描。
4. 勾选要迁移的东西，点开始迁移

## 隐私

代码里没凭据。没账号，没自建服务器（此处说的是没有中心化服务器即本项目提供一个默认的推荐方案但是去中心化），没统计，没广告。

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
