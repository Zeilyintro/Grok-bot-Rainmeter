# Grok bot-Rainmeter

[English](README.md) | **简体中文**

一个会变形、换表情的 Rainmeter 陪伴 bot，包含 **141 个样式**、平滑变形、黑白主题和可选鼠标视线跟随，也能单独换身体或表情。

![黑白主题与形态预览](docs/preview.png)

*预览图由皮肤实际几何生成，并非桌面截图。*

## 安装

在[最新发行页](https://github.com/Zeilyintro/Grok-bot-Rainmeter/releases/latest)下载 `Zeily-bot_4.0.rmskin`，双击安装，然后加载 `Bloub/Bloub.ini`。

已经安装？用 [Skins/Bloub](Skins/Bloub) 中的新版 `@Resources/Animation.lua` 替换原文件，再刷新即可保留自己的设置。

需要 Windows 10+、Rainmeter 4.5.26.3894+；安装包包含 32/64 位 MousePos 插件。

## 使用

- **左键**：切换下一个样式。
- **右键**：开关系统主题、白色主题、鼠标视线跟随。手动选色前先关闭系统主题跟随。
- **尺寸与速度**：修改 `Bloub.ini` 中的 `Size`、`Speed`，保存后刷新。中文 INI 保持 UTF-16 编码。

<details>
<summary>停留时间与变化偏好</summary>

在 `[Variables]` 中调整：

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

三项权重对应 **2–4 秒 / 8–15 秒 / 20–35 秒**，不必合计 100，0 禁用该档。`ShortBurstGuard=1` 减少连续短切换，0 关闭此限制。`Speed=1` 为原速，倍速不影响随机停留时长。

直立感叹号播完即切换；笔形态随机重放 2–4 次后切换，均不参与随机停留。

最后三项权重分别控制普通组合之间的**只换表情／只换身体／一起换**。0 禁用该类，三项全 0 恢复默认。近期样式避重，并避免连续三次同类型变化，因此实际比例会有变化。

141 个样式包括 **8 种身体 × 16 种表情**，以及 **13 个完整动画**。完整动画保留自己的眼睛动作和播放规则。

</details>

## 来源

原作：[Jérémy Perret / Bloub](https://github.com/jeremy-prt/bloub)，MIT 许可见 [LICENSE](LICENSE)。Rainmeter 改编由 Zeily 整理发布。

Bloub 重现了 x.ai bot 的视觉表现；本项目是非官方改编，与 x.ai 无关联。上游 MIT 许可覆盖代码，不覆盖其模仿的设计。

插件：[NSTechBytes / MousePos](https://github.com/NSTechBytes/MousePos)，原样附带，许可见 [Apache-2.0](licenses/MousePos-Apache-2.0.txt)。

皮肤版本为 4.2；用户制作的安装包保留 4.0 文件名及打包版本。验证采用离线模拟，实际帧率取决于桌面环境。
