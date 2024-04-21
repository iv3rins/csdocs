---
description: 本篇文章将介绍启动项以及分享参数。
---

# 启动项

+ 文章来源于totalcsgo.com。本手册仅作翻译。

启动选项是在启动《CS2》时应用的选项（或 "设置"）。它们可以做各种各样的事情，包括更改客户端的tickrate、设置FPS、自动加载CFG和调整其他高级选项。

在本页中，您可以找到所有已知的游戏启动项列表、以及TotalCS推荐您使用的启动项（即 CS2 的“最佳”启动项）。

## 启动项参数介绍

| 启动项 | 介绍 |
| ---- | ---- |
| `-vulkan` | 此启动选项会将游戏的渲染 API 从 DirectX 11 切换为 Vulkan。Vulkan 是一种较新的 3D 图形 API（2016 年发布），有可能会提高性能。（即更改渲染画面的技术，不稳定）|
| `-dxlevel [60 / 70 / 80 / 81 / 90 / 91 / 95 / 98 / 100 / 110]` | 更改 DirectX 的渲染版本。CS2 默认使用`110`（即-dxlevel 110），如果出现不稳定等情况，可以考虑更改此值。|
| `-allow_third_party_software` | 该启动选项允许第三方应用程序注入 CS2。某些软件（如 OBS Game Capture等录屏软件）在没有此启动选项的情况下可能无法运行。**注意**：此命令**可能**会降低您的信任因子（Trust Factor），从而**影响**您的对战体验（目前**尚不确定**是否会降低信任因子或其影响程度）。 |
| `-fullscreen` | 全屏启动 CS2 |
| `-refresh [刷新率]` |  有关于你的显示屏的参数，如果你的显示屏是 144Hz 的显示屏，建议更改为`-refresh 144` |
| `+exec [文件名（不用.cfg）]` | 每次启动时自动加载CFG文件。CFG文件应存放在 `Steam\SteamApps\common\Counter-Strike Global Offensive\game\csgo\cfg` 中 |
| `+mat_disable_fancy_blending 1` | 该启动项会禁用 纹理资源的混合（？）。可能会提升帧数 |
| `+cl_forcepreload 1` | 这其实是控制台命令。但经常被误以为是启动项。强制客户端预加载模型。可能会提升稳定性。 |
| `-high` | 该启动项会让CS2以高优先级运行。其实就是比低优先级先处理而已。 对帧数提升很小。|
| `-low` | 让CS2以低优先级运行。 |
| `-softparticlesdefaultoff` | 使CS2渲染的粒子不带有羽化效果。（用过PS的应该知道是什么） |
| `+fps_max [数值]` | 帧数限制 |
| `-nohltv` | 关闭CSTV（GOTV） |
| `-console` | 启用控制台 |
| `-nojoy` | 关闭手柄输入。减少占用内存。（据说急停辅助CFG就是通过手柄输入来实现自动急停的） |
| `-forcenovsync` | 关闭垂直同步。垂直同步会减少画面撕裂和功耗占用。但是会提高延迟。|
| `-threads [数值]` | 该启动选项设置 CS2 使用的处理器线程数量（例如，-threads 4 将使 CS2 使用 3 个线程）。我们建议您不要使用该启动项，因为它会导致不稳定和其他问题，一般来说，CS2 在管理线程使用方面做得很好。|
| `+violence_hblood 0` | 关闭溅血。 |
| `-language [语言]` | 让CS以指定语言启动。比如说`-language english`就是改成显示英文。|
| `-width [宽]` | CS2宽度的像素，比如说`-width 1920` |
| `-height [高]` | 同上，更改高度像素。 |
| `-x [偏移量]` | 让CS的画面在横向上偏移。 |
| `-y [偏移量]` | 同上。只不过是纵向偏移。 |
| `+r_dynamic [0 / 1]` | 这是一条控制台命令，通常被误认为是启动项。使用 "+r_dynamic 0 "禁用动态光照，或使用 "+r_dynamic 1 "启用动态光照（默认值）。将其设置为 0 可以略微提高 FPS，但会移除游戏中的一些照明功能，例如闪光弹在烟雾爆开时产生的闪光，这会导致无动态照明的负面影响大于正面影响。 |
| `+mat_queue_mode 2 ` | 将渲染画面队列改成异步进行，可能会提升帧率，但会导致不稳定。 |
| `-autoconfig` | 强制以游戏默认设置启动。 |

## 推荐参数

### 大众参数

`+fps_max 0 -nojoy -softparticlesdefaultoff +violence_hblood 0 +r_drawparticles 0 -console`

这是经过测试比较适合大众的启动项设置。（TOTALCS网站所述）

### 帧率极限参数

`+engine_low_latency_sleep_after_client_tick true +fps_max 0 -nojoy -high -fullscreen +mat_disable_fancy_blending 1 -forcenovsync +r_dynamic 0 +mat_queue_mode 2`

这是为了追求极限帧率的参数。

### 关闭VAC验证参数

`-insecure`

关闭CS的VAC，但是会导致你可能玩不了游戏。