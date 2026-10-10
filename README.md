# Grok bot-Rainmeter

**English** | [简体中文](README.zh-CN.md)

A little companion bot for Rainmeter with **141 styles**, smooth morphing, black and white themes, and optional mouse gaze tracking. Its body and expression can change independently.

![Black and white themes and sample shapes](docs/preview.png)

*Preview rendered from the skin's actual geometry, not a desktop screenshot.*

## Installation

Download `Zeily-bot_4.0.rmskin` from the [latest release](https://github.com/Zeilyintro/Grok-bot-Rainmeter/releases/latest), double-click to install, then load `Bloub/Bloub.ini`.

Already installed? Replace `@Resources/Animation.lua` with the version in [Skins/Bloub](Skins/Bloub), then refresh to keep your settings.

Requires Windows 10+ and Rainmeter 4.5.26.3894+. The installer includes both 32-bit and 64-bit MousePos plugins.

## Controls

- **Left-click:** switch to the next style.
- **Right-click:** toggle system theme following, the white theme, or mouse gaze tracking. Disable system theme following before choosing a theme manually.
- **Size and speed:** edit `Size` and `Speed` in `Bloub.ini`, save, then refresh the skin. Keep the INI file in its original UTF-16 encoding. The skin's context menu labels are currently in Chinese.

<details>
<summary>Timing and change preferences</summary>

Adjust these values under `[Variables]`:

```ini
Size=130
Speed=1
ShortWeight=25
NormalWeight=45
LongWeight=30
ShortBurstGuard=1
ExpressionChangeWeight=40
BodyChangeWeight=35
BothChangeWeight=25
```

The three weights correspond to **2–4 / 8–15 / 20–35 seconds**. They do not need to total 100; set a weight to 0 to disable that range. `ShortBurstGuard=1` reduces consecutive short dwells; 0 disables this guard. `Speed=1` is the original speed; playback speed does not scale random dwell times.

The upright exclamation mark switches after its animation ends. The pen-like shape repeats 2–4 times before switching. Neither uses random dwell times.

The last three weights choose **expression only / body only / both** for ordinary combinations. A weight of 0 disables that type; all three at 0 restore the defaults. The bot avoids recent styles and three identical change types in a row, so actual proportions may vary.

The 141 styles include **8 bodies × 16 expressions**, plus **13 complete animations**. Complete animations keep their own eye behavior and playback rules.

</details>

## Credits

Original: [Jérémy Perret / Bloub](https://github.com/jeremy-prt/bloub), licensed under [MIT](LICENSE). Rainmeter adaptation packaged and published by Zeily.

Bloub recreates the visual behavior of the x.ai bot avatar. This is an unofficial adaptation with no affiliation to x.ai. The upstream MIT license covers its code, not the design it imitates.

Plugin: [NSTechBytes / MousePos](https://github.com/NSTechBytes/MousePos), included unmodified; see [Apache-2.0](licenses/MousePos-Apache-2.0.txt).

Skin version: 4.2. The user-created installer retains its 4.0 filename and package version. Validation uses offline simulations; actual frame rates depend on the desktop environment.
