# Grok bot-Rainmeter

[English](README.md) | **简体中文**

一个会变形、换表情的 Rainmeter 陪伴 bot。基于 [Bloub](https://github.com/jeremy-prt/bloub) 改编，包含 **77 个样式、黑白主题、系统主题切换和可选鼠标视线跟随**。

![黑白主题与形态预览](docs/preview.png)

*预览图由安装包内的 Lua 几何生成，展示 6 个样式的两套主题，并非桌面截图。*

## 安装

在 Releases 下载 `Zeily-Bloud_4.0.rmskin`，双击安装，然后加载 `Bloub/Bloub.ini`。

需要 Windows 10+、Rainmeter 4.5.26.3894+；安装包包含 32/64 位 MousePos 插件。

## 使用

- **左键**：切换下一个样式。
- **右键**：开关系统主题、白色主题、鼠标视线跟随。手动选色前先关闭系统主题跟随。
- **尺寸与速度**：修改 `Bloub.ini` 中的 `Size`、`Speed`，保存后刷新。中文 INI 保持 UTF-16 编码。

<details>
<summary>停留时间与概率</summary>

在 `[Variables]` 中调整：

```ini
Size=130
Speed=1
ShortWeight=25
NormalWeight=45
LongWeight=30
ShortBurstGuard=1
```

三项权重对应 **2–4 秒 / 8–15 秒 / 20–35 秒**，不必合计 100，0 禁用该档。`ShortBurstGuard=1` 减少连续短切换，0 关闭此限制。`Speed=1` 为原速，倍速不影响随机停留时长。

直立感叹号播完即切换；笔形态随机重放 2–4 次后切换，均不参与随机停留。

</details>

## 来源

原作：[Jérémy Perret / Bloub](https://github.com/jeremy-prt/bloub)，MIT 许可见 [LICENSE](LICENSE)。Rainmeter 改编由 Zeily 整理发布。

Bloub 重现了 x.ai bot 的视觉表现；本项目是非官方改编，与 x.ai 无关联。上游 MIT 许可覆盖代码，不覆盖其模仿的设计。

插件：[NSTechBytes / MousePos](https://github.com/NSTechBytes/MousePos)，原样附带，许可见 [Apache-2.0](licenses/MousePos-Apache-2.0.txt)。

发布包版本为 4.0，内部皮肤 Metadata 保留 3.8 标记。离线模拟检查不代表实际桌面帧率。
