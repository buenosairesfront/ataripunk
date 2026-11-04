[English](README.md) · **Español** · [Français](README.fr.md) · [Deutsch](README.de.md) · [日本語](README.ja.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md)

# U-MA Atari Punk

Una Atari Punk Console para armar en pantalla: dos NE555, uno como reloj y otro como pulso que sólo vuelve a dispararse cuando terminó. Cambiá cada pieza menos los dos 555, mirala en un osciloscopio de cuatro canales y escuchá el resultado en vivo.

**▶ Abrir la app:** https://buenosairesfront.github.io/ataripunk/

No hay nada que instalar.

## Cómo funciona

### Osciloscopio
Arriba, cuatro trazos: tensión de C1 (pata 6 de IC1), salida de IC1, tensión de C2 (pata 6 de IC2) y la señal en el parlante. Lecturas de frecuencia del reloj, duración del pulso, división ÷n y nota de salida.

### 01 · El circuito
El esquema completo. Tocá una pieza para editarla: batería (4,5–15 V), R1, R2, R3, los potes VR1 y VR2 (valor, posición del eje y curva A/B), C1, C2, C3 y el parlante. Con el deslizador, por valores comerciales E12/E6, o escribiéndolo como en la placa: `4k7`, `10n`, `100u`, `2M2`. Los dos NE555 quedan fijos. Cinco recetas: Clásica, Grave, Chirrido, Muchos pasos, Lo-fi 5 V.

### 02 · Tocar
Un pad XY (X = VR1, Y = VR2) cuyo fondo es un mapa pixelado de las divisiones: cada color es un ÷n distinto y el brillo es la altura. Perillas de VR1, VR2 y volumen, y modo Gate para que suene sólo mientras tocás.

### 03 · La escalera
La frecuencia de salida según el eje de VR1. La línea punteada es el reloj; la gruesa es lo que suena, cortada donde salta la división. Ése es el sonido de escalones de la Atari Punk.

### 04 · La placa
Una placa ilustrativa con piezas como las reales: las bandas de las resistencias, los códigos de los cerámicos (103 = 10 nF) y los ejes de los potes siguen tus valores; desde 1 µF el condensador pasa a electrolítico.

### 05 · Lista de materiales
Las piezas con sus valores y códigos actuales, lista para copiar.

## Por dentro

Un solo `index.html` sin dependencias. El sonido sale de un modelo exacto por eventos de los dos 555 (astable 0,693·(R1+VR1)·C1 / 0,693·VR1·C1, monoestable 1,1·(R2+VR2)·C2) que corre muestra por muestra en un AudioWorklet, con el pasa-altos que forman C3 y la carga. Es una aproximación: no tiene en cuenta la carga sobre la salida del 555.

## Correr local

Bajá `index.html` y abrilo, o serví la carpeta:

```
python3 -m http.server 8000
```

<!-- u-ma:more -->
**Más de U-MA:** todos los instrumentos y herramientas en un solo lugar → [muestrario U-MA](https://github.com/buenosairesfront/U-ma/blob/main/README.es.md)
<!-- /u-ma:more -->

## Créditos

Atari Punk Console: diseño original de Forrest M. Mims III (Stepped Tone Generator). App de U-MA サウンド · [Buenos Aires Front](https://www.instagram.com/buenos.aires.front/).
