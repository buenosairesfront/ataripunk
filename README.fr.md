[English](README.md) · [Español](README.es.md) · **Français** · [Deutsch](README.de.md) · [日本語](README.ja.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md)

# U-MA Atari Punk

Une Atari Punk Console à monter à l'écran : deux NE555, l'un en horloge, l'autre en impulsion qui ne se redéclenche qu'une fois terminée. Changez chaque composant sauf les deux 555, observez-la sur un oscilloscope à quatre voies et écoutez le résultat en direct.

**▶ Ouvrir l'application :** https://buenosairesfront.github.io/ataripunk/

Rien à installer. L'interface est en espagnol.

## Comment ça marche

### Oscilloscope
En haut, quatre traces : tension de C1 (broche 6 d'IC1), sortie d'IC1, tension de C2 (broche 6 d'IC2) et signal du haut-parleur. Affichage de la fréquence d'horloge, de la durée d'impulsion, de la division ÷n et de la note de sortie.

### 01 · Le circuit
Le schéma complet. Touchez un composant pour le modifier : pile (4,5–15 V), R1, R2, R3, potentiomètres VR1 et VR2 (valeur, position de l'axe, courbe A/B), C1, C2, C3 et le haut-parleur. Curseur, valeurs normalisées E12/E6 ou saisie comme sur une carte : `4k7`, `10n`, `100u`, `2M2`. Les deux NE555 sont verrouillés. Cinq préréglages. Alimentation au choix : pile 9 V ou USB 5 V (R3 passe à 100 Ω pour garder le niveau). Enregistrez vos combinaisons avec un nom.

### 02 · Jouer
Un pad XY (X = VR1, Y = VR2) dont le fond est une carte pixelisée des divisions : chaque couleur est un ÷n, la luminosité est la hauteur. Boutons VR1, VR2 et volume, et mode Gate.

### 03 · L'escalier
La fréquence de sortie selon l'axe de VR1. Pointillé : l'horloge ; trait épais : ce que l'on entend, coupé là où la division saute. C'est le son en escalier de l'Atari Punk.

### 04 · La carte
Une carte illustrative aux composants réalistes : anneaux de couleur, codes céramiques (103 = 10 nF) et axes des potentiomètres suivent vos valeurs ; dès 1 µF, le condensateur devient électrolytique.

### 05 · Nomenclature
Export de la liste en planche PNG au style U-MA : valeurs, codes, mesures, pad XY et escalier.

## Sous le capot

Un seul `index.html` sans dépendances. Le son vient d'un modèle événementiel exact des deux 555, calculé échantillon par échantillon dans un AudioWorklet, avec le passe-haut formé par C3 et la charge. C'est une approximation : la charge sur la sortie du 555 est ignorée.

## Lancer en local

Téléchargez `index.html` et ouvrez-le, ou servez le dossier :

```
python3 -m http.server 8000
```

<!-- u-ma:more -->
**Plus de U-MA :** tous les instruments et outils au même endroit → [vitrine U-MA](https://github.com/buenosairesfront/U-ma/blob/main/README.fr.md)
<!-- /u-ma:more -->

## Crédits

Atari Punk Console : conception originale de Forrest M. Mims III (Stepped Tone Generator). Application par U-MA サウンド · [Buenos Aires Front](https://www.instagram.com/buenos.aires.front/).
