# 冒险岛 · iOS 离线移植

当前方向是读取真实冒险岛资源的客户端移植。**此前 61.6 KB 的 MaplePocket IPA 是独立绘制的旧样机，不是冒险岛复刻；不要将它当作当前版本。**

## 真正资源与客户端

- 原版 WZ 资源包已在工作流中实际下载并检查，大小 1,765,661,358 字节。包含真实 Character / Map / Mob / Npc / UI / Sound 等数据。
- OpenMS 历史离线客户端固定于 `3e379cfb05beb29ae8413352c8a3345783eb35da`。射手村及相邻三张已选地图编号为 `100000000`, `100000001`, `100000002`；实际是三张地图，不是完整世界。
- 独立的真实 C++ / WASM 客户端编译验证也已通过，固定上游 nmnsnv/maplestory-wasm 的 `9eef4c730ff5639089eeccae51bf6266c878c30c`；它是备选技术路线，不等于已通过 iOS 游戏验证。
- 旧 NX 资源 Google Drive 链接实测无法下载，未当作可用输入。

## iOS 安装包

打开 [Actions](https://github.com/use3099/-ms079-ios/actions)，选择 **Build original-art offline iOS IPA**。只有成功的运行才提供 `MapleOriginal-iOS-unsigned` 安装包产物。下载后解压，取得 `MapleOriginal-unsigned.ipa`，用自己的签名方式安装。不要把源码 ZIP 当作 IPA。

流程在同一台构建机中提取原版资源、编译离线客户端、安装到 iPhone 模拟器并等待客户端就绪，然后才编译真机 IPA。只上传用户请求的 IPA、校验值和运行诊断，不发布独立网页素材包。编译和模拟器通过仍不能代替真机操作验证。

## 范围

此阶段目标是原版 v83 资源的三地图离线 iOS 版，带触屏方向、跳跃、攻击、拾取、背包、技能和菜单按键。真实可用性以模拟器和真机测试结果为准。不是完整 v079，不保证兼容最初的 Java 服务端；连接自建服务器仍需后续协议适配。

## 源码与许可

`MapleOriginal-iOS-host-source-v2.zip` 包含 iOS 承载源码。开源游戏实现来源于 [OpenMS](https://github.com/tensorfish/openms)，项目当前许可为 GPL-3.0-or-later；构建包包含项目许可证及固定源码地址。原版游戏美术、音乐和数据仍属于其各自权利人，开源代码许可不涵盖这些资产。
