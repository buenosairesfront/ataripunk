[English](README.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [日本語](README.ja.md) · **中文** · [हिन्दी](README.hi.md)

# U-MA Atari Punk

在屏幕上搭建的 Atari Punk Console：两颗 NE555，一颗作时钟，一颗作脉冲，只有脉冲结束后才会再次触发。除两颗 555 外的所有元件都可更换，在四通道示波器上观察，并实时听到结果。

**▶ 打开应用：** https://buenosairesfront.github.io/ataripunk/

无需安装。界面为西班牙语。

## 使用方法

### 示波器
顶部四条波形：C1 电压（IC1 第 6 脚）、IC1 输出、C2 电压（IC2 第 6 脚）和扬声器信号。显示时钟频率、脉冲宽度、分频 ÷n 和输出音名。

### 01 · 电路
完整原理图。点任一元件即可编辑：电池（4.5–15 V）、R1、R2、R3、电位器 VR1 和 VR2（阻值、转轴位置、A/B 曲线）、C1、C2、C3 和扬声器。可用滑块、E12/E6 标准值，或按电路板写法输入：`4k7`、`10n`、`100u`、`2M2`。两颗 NE555 锁定。五种预设。电源可选 9 V 电池或 5 V USB（R3 改为 100 Ω 以保持音量）。可按名称保存自己的组合。

### 02 · 演奏
XY 触控板（X = VR1，Y = VR2），背景是分频的像素图：每种颜色是一个 ÷n，亮度代表音高。VR1、VR2 和音量旋钮，以及 Gate 模式。

### 03 · 阶梯
输出频率随 VR1 转轴位置的变化。虚线是时钟，粗线是实际听到的声音，在分频跳变处断开。这就是 Atari Punk 的阶梯音色。

### 04 · 电路板
用逼真元件绘制的示意电路板：色环、瓷片电容代码（103 = 10 nF）和电位器转轴随数值变化；1 µF 及以上的电容画成电解电容。

### 05 · 元件清单
将元件表导出为 U-MA 风格的 PNG：数值、代码、读数、XY 触控板和阶梯图。

## 内部原理

单个 `index.html`，无依赖。声音来自对两颗 555 的事件级精确模型，在 AudioWorklet 中逐样本计算，并经过 C3 与负载形成的高通。这是近似模型，未考虑 555 输出端的负载。

## 本地运行

下载 `index.html` 直接打开，或启动本地服务：

```
python3 -m http.server 8000
```

<!-- u-ma:more -->
**更多 U-MA 作品：** 所有乐器和工具汇集一处 → [U-MA 作品集](https://github.com/buenosairesfront/U-ma/blob/main/README.zh.md)
<!-- /u-ma:more -->

## 致谢

Atari Punk Console：Forrest M. Mims III 原创设计（Stepped Tone Generator）。应用：U-MA サウンド · [Buenos Aires Front](https://www.instagram.com/buenos.aires.front/)。
