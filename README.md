# Grok bot-Rainmeter

**English** | [简体中文](README.zh-CN.md)

A Rainmeter desktop companion with more emotion and a stronger sense of companionship. It responds to your pointer through expressions, develops a personality through interaction and sways with music. The current version is **5.0 (171 styles)**. The previous published version is 4.2 (141 styles).

![Black and white themes, shapes and interaction](docs/preview.png)

*The introduction is drawn statically from v28 pose and outline data, not a desktop screenshot. It shows representative styles, not all 171. Editable source: [preview.html](docs/preview.html).*

## Features

- **Emotion is the central addition:** expressions now respond to interaction. Approaching gradually opens a smile; sudden approaches can startle it, repeated fast passes build impatience and anger, and sustained circles or broad strokes can cause dizziness. Emotions accumulate and gradually decay, shaping its expression and gaze.
- **Personality and affinity:** natural growth, clingy, aloof and timid modes produce different responses. Interaction slowly influences bravery, clinginess, patience and energy; growth and affinity persist in Settings.inc.
- **Music motion:** built-in output monitoring, tempo tracking and predicted beats drive side-to-side sway, subtle bounce and floating notes. Dancing retains autonomous dwell/change selection while suppressing complete actions. Interaction and dizziness take priority. Some songs can still drift to secondary rhythms or synchronize poorly.
- **A more natural autonomous rhythm:** original dwell weights and selection remain, with emotion-aware presentation, occasional spontaneous ^^, boredom and brief naps. Ordinary styles have a 3-second guard after morph completion; actions return to the current emotion. Interaction does not move the skin window.
- **171 styles and themes:** star and flower join the original eight bodies; 16 base expressions and 13 complete actions remain, minus two unsuitable drop combinations. Comfort and spiral-eye overlays are new. Smooth morphing, black/white themes and system theme following are inherited features.

## Compared with GitHub 4.2

| Focus | Published 4.2 | Current 5.0 |
|---|---|---|
| Emotion and interaction | Random styles and optional pointer gaze | Accumulating/decaying emotions, gesture reactions, comfort and spiral eyes |
| Personality | No growth system | Natural growth or three fixed personalities, persistent affinity |
| Music | No audio monitoring or dance | Tempo tracking, predicted beats, sway, bounce and notes |
| Autonomous rhythm | Dwell weights, recent avoidance and action bag | Same foundation with display guards, emotion-aware returns, boredom/naps and conflict handling |
| Styles | 8 bodies, 141 styles | 10 bodies, 171 styles; base expression/action counts unchanged |
| Controls | Left-click switching and 3 menu switches | Left-click switching removed; 8 menu entries |

Comparison uses the [GitHub v4.2 README](https://github.com/Zeilyintro/Grok-bot-Rainmeter/blob/v4.2/README.md), its INI/Lua, and local 5.0 code. Emotion/personality leads the introduction, followed by music, autonomous rhythm and styles. Themes, smooth morphing and pointer gaze are inherited capabilities.

## Installation and upgrade

Requires Windows 10+ and Rainmeter 4.5.26.3894+. MousePos supplies pointer coordinates; music uses Rainmeter's built-in AudioLevel with no additional music plugin.

Download **Zeily-bot_5.0.rmskin** from the [5.0 release](https://github.com/Zeilyintro/Grok-bot-Rainmeter/releases/tag/v5.0), double-click to install, then load `Bloub/Bloub.ini`. The complete installer includes Settings.inc and both MousePos architectures; no additional music plugin is needed.

Before upgrading, back up installed Bloub.ini and @Resources/Settings.inc. Preserve personal Size, Speed, weights and theme/interaction switches after installation. Merge or restore your previous Settings.inc to retain personality growth and affinity. Do not delete the installed skin first.

Upgrading from 4.2 or early test versions requires the complete INI and Lua, not a Lua-only replacement. Debug defaults to 0; set it to 1 when needed. For manual plugin installation, use only the DLL matching Rainmeter's architecture.

## Controls

The native context menu controls system theme, white theme, mouse gaze, mouse interaction, music motion, interaction intensity, personality and growth/affinity reset. Menu labels are Chinese. Disable system theme following before choosing a manual theme.

Edit Size, Speed and dwell/change weights in Bloub.ini, then refresh. Preserve UTF-16LE BOM for INI and ASCII for Lua. Auto/full/restrained interaction modes control gesture scope and thresholds, not motion amplitude or speed. Optional MusicSway, MusicLead and MusicBounce settings are described in the [Chinese usage notes](TEST-NOTES.zh-CN.md).

## Status and limitations

5.0 is based on the final v28 code. No offline simulations, Lua loading/execution or desktop tests were run for v13–v28. File and artwork checks do not prove native operation. Real-song accuracy, latency, FPS, CPU and configuration persistence remain unverified; music synchronization is not claimed to be fixed. Guards and emotion overrides affect autonomous selection, so seeing every style in a short session is not guaranteed.

Source, skin and installer versions are all 5.0. Settings.inc provides initial configuration; preserve personal settings during upgrades.

- [Usage, upgrade and observation notes (Chinese)](TEST-NOTES.zh-CN.md)
- [History and old validation (Chinese)](docs/DEVELOPMENT-HISTORY.zh-CN.md)

## Credits and licenses

Original: [Jérémy Perret / Bloub](https://github.com/jeremy-prt/bloub), [MIT](LICENSE). Rainmeter adaptation by Zeily. MousePos by [NSTechBytes](https://github.com/NSTechBytes/MousePos), with its [Apache-2.0](licenses/MousePos-Apache-2.0.txt) license retained. This is an unofficial recreation of the x.ai bot's visual behavior with no affiliation to x.ai. The upstream license covers code, not the design it imitates.

<details>
<summary>Original 4.2 release documentation (historical controls and installation)</summary>

The following original text applies to 4.2 only. It must not be used to restore left-click switching in the current version or to justify a Lua-only first upgrade. The preview remains the 4.2 baseline.

A little companion bot for Rainmeter with **141 styles**, smooth morphing, black and white themes, and optional mouse gaze tracking. Its body and expression can change independently.

![Black and white themes and sample shapes](docs/preview-v4.2.png)

*Preview rendered from the skin's actual geometry, not a desktop screenshot.*

## Installation

Download `Zeily-bot_4.0.rmskin` from the [latest release](https://github.com/Zeilyintro/Grok-bot-Rainmeter/releases/tag/v4.2), double-click to install, then load `Bloub/Bloub.ini`.

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

</details>
