**English** · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [日本語](README.ja.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md)

# U-MA Atari Punk

An Atari Punk Console you can rebuild on screen: two NE555 timers, one running as a clock and one as a pulse that only re-fires when it has finished. Change every part except the two 555s, watch it on a four-channel scope and hear the result live.

**▶ Open the app:** https://buenosairesfront.github.io/ataripunk/

Nothing to install. The interface is in Spanish.

## How it works

### Scope
At the top, four traces: C1 voltage (pin 6 of IC1), IC1 output, C2 voltage (pin 6 of IC2) and the speaker signal. Readouts show clock frequency, pulse length, division ÷n and the output note.

### 01 · The circuit
Full schematic. Tap any part to edit it: battery (4.5–15 V), R1, R2, R3, pots VR1 and VR2 (value, shaft position and A/B taper), C1, C2, C3 and the speaker. Use the slider, step through E12/E6 standard values, or type it like on a board: `4k7`, `10n`, `100u`, `2M2`. The two NE555s are locked. Five presets: Classic, Low, Chirp, Many steps, Lo-fi 5 V. Power switch: 9 V battery or 5 V USB (R3 drops to 100 Ω to keep the level). Save your own combinations by name.

### 02 · Play
An XY pad (X = VR1, Y = VR2) whose background is a pixel map of the divisions: each colour is a different ÷n, brightness is pitch. Knobs for VR1, VR2 and volume, and a Gate mode that only sounds while you touch the pad.

### 03 · The staircase
Output frequency against VR1's shaft position. The dashed line is the clock; the thick line is what you hear, broken into segments where the division jumps. That is the stepped sound of the Atari Punk.

### 04 · The board
An illustrative board with real-looking parts: resistor colour bands, ceramic codes (103 = 10 nF) and pot shafts follow your values; caps of 1 µF or more turn into electrolytics.

### 05 · Bill of materials
Export the list as a PNG sheet in the U-MA look: values, codes, readings, the XY pad and the staircase.

## Under the hood

A single `index.html` with no dependencies. The sound comes from an event-exact model of the two 555s (astable 0.693·(R1+VR1)·C1 / 0.693·VR1·C1, monostable 1.1·(R2+VR2)·C2) running sample by sample in an AudioWorklet, with the high-pass formed by C3 and the load. It is an approximation: it ignores output loading of the 555.

## Run locally

Download `index.html` and open it, or serve the folder:

```
python3 -m http.server 8000
```

<!-- u-ma:more -->
**More from U-MA:** every instrument and tool in one place → [U-MA showcase](https://github.com/buenosairesfront/U-ma)
<!-- /u-ma:more -->

## Credits

Atari Punk Console: original design by Forrest M. Mims III (Stepped Tone Generator). App by U-MA サウンド · [Buenos Aires Front](https://www.instagram.com/buenos.aires.front/).
