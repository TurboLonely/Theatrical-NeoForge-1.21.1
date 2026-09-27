# Theatrical — NeoForge 1.21.1 (Unofficial Port)

> **This is an unofficial, community-made port.** It is **not** affiliated with, endorsed by, or
> supported by the original authors. All credit for the mod itself goes to the original
> Theatrical team — see [Credits & Attribution](#credits--attribution).
>
> **这是一个非官方移植版**，与原作者团队无隶属关系，也未获得其背书或支持。模组本体的全部
> 功劳归原作者团队所有，详见下方的署名与致谢章节。

A port of [Theatrical](https://github.com/theatricalmod/Theatrical) to **Minecraft 1.21.1 /
NeoForge**, built on [Architectury](https://github.com/architectury).

Theatrical is a mod all about adding equipment from the live events industry — tungsten lights,
LEDs, moving heads, sound systems, rigging equipment, stage setups, and lighting control systems.

---

## About this port

This repository is **NeoForge-only**. The upstream multi-loader layout was reduced so that only the
NeoForge target is built:

| | Upstream | This port |
|---|---|---|
| Loaders | Fabric + Forge | **NeoForge only** |
| Minecraft | 1.20.x / in-progress 1.21.x | **1.21.1** |
| Modules | `common`, `fabric`, `forge` | `common`, `neoforge` |

Work done in this port, on top of the upstream `ver/1.21.1` branch:

- Removed the `fabric` and `forge` modules and reworked `settings.gradle` / `build.gradle` so only
  `common` + `neoforge` are built.
- Completed the Minecraft 1.20.2 → 1.21.1 API migration (rendering / vertex API, data components,
  `RegistryFriendlyByteBuf`-based networking, screen input handling, and more).
- Reworked the networking layer for the NeoForge payload system.
- Dropped the optional Shimmer compatibility layer (`compat/ModCompat`, `compat/ShimmerCompat`) and
  its mixin plugin hooks.
- Aligned the mod metadata `license` field with the repository `LICENSE` (MIT).

Upstream features, content, textures and assets are unchanged.

---

## Requirements

| | Version |
|---|---|
| Minecraft | 1.21.1 |
| Mod loader | NeoForge 21.1.x (built against 21.1.251) |
| Architectury API | 13.x |
| Java | 21 |

**Required dependency:** [Architectury API](https://www.curseforge.com/minecraft/mc-mods/architectury-api)
(NeoForge, 13.x). The mod will not load without it. It is **not** bundled.

## Installation

1. Install Minecraft 1.21.1 with **NeoForge**.
2. Drop [Architectury API](https://www.curseforge.com/minecraft/mc-mods/architectury-api) (NeoForge 13.x) into your `mods` folder.
3. Drop the Theatrical jar from the [Releases](../../releases) page into your `mods` folder.
4. Launch the game.

## Downloads

Grab the latest jar from the [**Releases**](../../releases) page of this repository.

Each release ships:

- `Theatrical-neoforge-<version>+mc1.21.1.jar` — the mod itself.
- `Theatrical-汉化资源包.zip` — an **optional** Simplified Chinese translation resource pack
  (contributed separately, not part of the mod). Enable it in *Options → Resource Packs*.

## Building from source

```bash
# JDK 21 required
./gradlew :neoforge:build
```

The mod jar is produced in `neoforge/build/libs/`. Use the plain
`Theatrical-neoforge-<version>+mc1.21.1.jar` (not `-dev-shadow` or `-sources`) for installation.

To run a development client:

```bash
./gradlew :neoforge:runClient
```

---

## Credits & Attribution

**Original mod — all credit belongs to the Theatrical team:**

- Repository: [theatricalmod/Theatrical](https://github.com/theatricalmod/Theatrical)
- CurseForge: [Theatrical](https://www.curseforge.com/minecraft/mc-mods/theatrical)
- Discord: [Join the Discord](https://discord.gg/7qMs5d6)
- Development streams: [twitch.tv/Rushmead](https://twitch.tv/Rushmead)

Contributors:

- Rushmead
- bright_spark
- FreneticScribbler
- Dumaan089

This port is maintained by [TurboLonely](https://github.com/TurboLonely). Please **do not** report
bugs in this port to the original authors — open an issue in this repository instead. For the
original mod on supported versions, use the upstream CurseForge page.

## License

Licensed under the **MIT License**, the same license as the upstream project.

```
MIT License

Copyright (c) 2025 Stuart Pomeroy
```

See [LICENSE](LICENSE) for the full text. The original copyright notice and permission notice are
retained, as required by the license. If you redistribute this or a modified version, keep the
`LICENSE` file and this attribution intact.

---

## 中文说明

**这是一个非官方移植版**，将 [Theatrical](https://github.com/theatricalmod/Theatrical) 移植到
**Minecraft 1.21.1 + NeoForge**。模组本体由原作者团队开发，版权归其所有（MIT 协议），本仓库
仅为 NeoForge 1.21.1 的适配版本，与原作者团队无关。

**环境要求：** Minecraft 1.21.1、NeoForge 21.1.x、Architectury API 13.x、Java 21。

**安装：** 安装 NeoForge 后，把 Architectury API 与本模组的 jar 一起放进 `mods` 文件夹即可。

**本移植版改动：** 移除 Fabric / Forge 模块（仅保留 NeoForge）、完成 1.21.1 API 迁移、
重做网络层、移除可选的 Shimmer 兼容层。模组内容与材质资源未做改动。

**汉化资源包：** 每个 Release 附带一个可选的简体中文资源包
`Theatrical-汉化资源包.zip`，在「选项 → 资源包」中启用即可，不启用不影响游戏。

**反馈：** 本移植版的问题请在本仓库提 Issue，请勿打扰原作者。
