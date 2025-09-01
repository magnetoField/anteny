---
layout: default
---

# Agenda

- Wprowadzenie do teorii fal elektromagnetycznych.
- Czym jest NEC oraz ItsHF.
- Czym jest SWR i sposoby jego minimalizacji.
- Założenia projektowe anten.
- Parametryzacja anteny w programie 4nec2.
- Badanie dipola: SWR vs wysokość rozwieszenia, SWR vs średnica drutu.
- Wykreślenie predykcji propagacji dla wybranych pasm KF.
- Optymalizacja anteny pod względem SWR.
- Wyznaczanie parametrów obwodu dopasowującego impedancję.
- Wyznaczenie charakterystyki promieniowania.
- Wyznaczenie promieniowania w strefie bliskiej (BHP - strefy promieniowania EM). 
- Wyznaczenie charakterystyki częstotliwościowej.
- Badanie anteny kierunkowej typu Uda-Yagi.
- Projektowanie własnej anteny kierunkowej z wykorzystaniem heurystycznego algorytmu genetycznego.
- Wykreślenie charakterystyki częstotliwościowej na wykresie Smitha.
- Wprowadzanie geometri dla anteny helikalnej oraz talerza satelitarnego.
- Wykreślenie predykcji propagacji dla anteny kierunkowej.
- Zalecana literatura.

# Instalacja programu

### [https://www.qsl.net/4nec2/](https://www.qsl.net/4nec2/)  

![Direct_antena_beam](https://www.qsl.net/4nec2/Home_files/image005.gif)

# Równania Maxwella

| Postać różniczkowa | Postać całkowa | Sens fizyczny równania |
| :---: | :---: | :--- |
| $\nabla \times \vec{E} = -\frac{\partial \vec{B}} {\partial {t}}$ | $\oint\limits_L \vec{E} \cdot \text{d}\vec{l} = -\frac{\text{d}\Phi_B}{\text{d}t}$ <br /> gdzie $\Phi_B$ – strumień magnetyczny przez dowolny kontur rozpięty na krzywej L | Zmienne w czasie pole magnetyczne wytwarza pole elektryczne. |
| $\nabla \times \vec{B} = \mu \vec{j} +\mu \varepsilon \frac{\partial \vec{E}} {\partial {t}}$ | $\oint\limits_L \vec{B} \cdot \text{d}\vec{l} = \mu I + \mu \varepsilon \frac{\text{d}\Phi_E}{\text{d}t}$ <br /> gdzie $\Phi_E$ – strumień elektryczny przez dowolny kontur rozpięty na krzywej L, a $I$ – całkowity prąd elektryczny przecinający ten kontur | Przepływający prąd oraz zmienne pole elektryczne wytwarzają pole magnetyczne. |
| $\varepsilon \nabla \cdot \vec{E} = \rho$ | $\varepsilon \oint\limits_S \vec{E} \cdot \text{d}\vec{S} = q$ <br /> gdzie $q$ – całkowity ładunek zawarty wewnątrz powierzchni $S$ | Ładunki są źródłem pola elektrycznego. |
| $\nabla \cdot \vec{B} = 0$ | $\oint\limits_S \vec{B} \cdot \text{d}\vec{S} = 0$ | Pole magnetyczne jest bezźródłowe. |  
  
  

# Numerical Electromagnetics Code

- 1975 Nec
- 1992 Nec-4
- Metoda numeryczna rozwiązywania równań Maxwella 

![Obraz](https://images-provider.frontiersin.org/api/ipx/w=480&f=webp/https://www.frontiersin.org/files/Articles/1178466/fphy-11-1178466-HTML/image_m/fphy-11-1178466-g003.jpg)



## Standing Wave Ratio

![Swar](https://upload.wikimedia.org/wikipedia/commons/7/7a/Standing_wave_ratio_%28showing_Vmin_and_Vmax%29.png)


![betterSWR](https://upload.wikimedia.org/wikipedia/commons/3/37/Standing_wave_SWR_1_%28forward%2C_reflected%29.gif)
- SWR = 1  

![swrjedenpol](https://upload.wikimedia.org/wikipedia/commons/3/32/Standing_wave_SWR_1.5_%28traveling%2C_standing%29.gif)  
- SWR = 1.5  

![swrdwatrzytrzy](https://upload.wikimedia.org/wikipedia/commons/c/cc/Standing_wave_SWR_2.33_%28traveling%2C_standing%29.gif)  
- SWR = 2.3  

![swrcztery](https://upload.wikimedia.org/wikipedia/commons/6/6d/Standing_wave_SWR_4_%28traveling%2C_standing%29.gif)  
- SWR = 4  


---

Współczynnik fali stojącej (SWR) definiuje się jako stosunek amplitudy maksymalnej (w strzałce fali stojącej) do amplitudy minimalnej (w węźle fali stojącej) w linii zasilającej odbiornik. W linii przesyłającej falę elektromagnetyczną mierzoną wielkością jest **napięcie elektryczne**.

$$\text{SWR} = \frac{|V_\text{max}|}{|V_\text{min}|}$$

Maksymalna amplituda fali w linii jest równa sumie amplitud fali padającej i odbitej, a minimalna różnicy tych amplitud. Amplitudę fali odbitej określa **współczynnik odbicia ($\Gamma$)**, który zależy od impedancji linii. Pamiętając, że moc fali jest proporcjonalna do kwadratu jej amplitudy:

$$\Gamma = \frac{V_r}{V_f} = \frac{Z_L - Z_o}{Z_L + Z_o}$$

$$
\begin{align}
|V_\text{max}| &= |V_f| + |V_r| \\
&= |V_f| + |\Gamma V_f| \\
&= (1 + |\Gamma|) |V_f|.
\end{align}
$$

$$
\begin{align}
|V_\text{min}| &= |V_f| - |V_r| \\
&= |V_f| - |\Gamma V_f| \\
&= (1 - |\Gamma|) |V_f|.
\end{align}
$$

Podstawiając te wartości, otrzymujemy wzór na SWR:

$$\text{SWR} = \frac{|V_\text{max}|}{|V_\text{min}|} = \frac{1 + |\Gamma|}{1 - |\Gamma|}$$

A także w zależności od mocy:

$$\text{SWR} = \frac{1 + \sqrt{P_r/P_f}}{1 - \sqrt{P_r/P_f}}$$

gdzie:
* $V_f, P_f$ – amplituda i moc fali padającej,
* $V_r, P_r$ – amplituda i moc fali odbitej.
* $\Gamma$ – współczynnik odbicia.

Współczynnik fali stojącej (SWR) może przyjmować wartości od 1 do nieskończoności ($\infty$).

* **SWR = 1**
    Amplituda fali odbitej jest równa 0, a cała moc ze źródła jest dostarczana do odbiornika. Jest to idealne dopasowanie, gdy impedancja obciążenia ($Z_L$) jest równa impedancji linii ($Z_o$).
* **SWR > 1**
    Obciążenie jest niedopasowane do linii, co powoduje powstanie fali odbitej, która wraca do nadajnika. Bardzo wysoki SWR może uszkodzić **linię transmisyjną** lub nawet nadajnik.

Do pomiaru SWR stosuje się pasywne urządzenia zwane **reflektometrami**.

![SWRvsPower](https://0x9900.com/images/SWR/VSWR.svg)

## Transformator

![Transformer](https://circuitdigest.com/sites/default/files/projectimage_tut/Impedance-Matching-Transformers-Circuit.png)

## Baluny i Ununy

![Balun](https://www.electronics-notes.com/images/antenna-efhw-unun-tuner-set-up-01.svg)

![Unun](https://www.electronics-notes.com/images/antenna-unun-balun-differences-01.svg)
---

## Założenia projektowe anten
- Aplikacja
- Pasmo
- Jednopasmowa czy wielopasmowa
- Apertura
- Charakterystyka promieniowania
- Moc
- Zasięg

## Input Cards
```
Wire Specification (GW)
Purpose:  To generate a string of segments to represent a straight wire.

Card:
           Cols  Parameter
          ----------------
           1- 2  GW
           3- 5  I1 - ITG
           6-10  I2 - NS
          11-20  F1 - XW1
          21-30  F2 - YW1
          31-40  F3 - ZW1
          41-50  F4 - XW2
          51-60  F5 - YW2
          61-70  F6 - ZW2
          71-80  F7 - RAD

          The above card defines a string of segments with radius RAD.  If
          RAD is zero or blank, a second card is read to set parameters to
          taper the segment lengths and radius from one end of the wire to
          the other.  The format for the second card (GC), which is read
          only when RAD is zero, is:

           Cols  Parameter
          ----------------
           1- 2  GC
           3- 5  blank
           6-10  blank
          11-20  F1 - RDEL
          21-30  F2 - RAD1
          31-40  F3 - RAD2
          41-50  blank
          51-60  blank
          61-70  blank
          71-80  blank


Parameters:
        Integers
           ITG   (I1) - Tag number assigned to all segments of the wire.

           NS    (I2) - Number of segments into which the wire will be
                        divided.

        Decimal Numbers
           XW1   (F1) - X coordinate  \
                                       \
           YW1   (F2) - Y coordinate    >  of wire end 1
                                       /
           ZW1   (F3) - Z coordinate  /

           XW2   (F4) - X coordinate  \
                                       \
           YW2   (F5) - Y coordinate    > of wire end 2
                                       /
           ZW2   (F6) - Z coordinate  /

           RAD   (F7) - Wire radius, or zero for tapered segment option.

       Optional GC card parameters

           RDEL  (F1) - Ratio of the length of a segment to the length of the
                        previous segment in the string.

           RAD1  (F2) - Radius of the first segment in the string.

           RAD2  (F3) - Radius of the last segment in the string.

           The ratio of the radii of adjacent segments is

                        RRAD = (RAD2/RAD1)^(1/(NS-1))

           If the total wire length is L, the length of the first segment is

                        S1 = L(1-RDEL)/(1-RDEL^NS)

           or

                        S1 = L/NS if RDEL=1.

Notes:
- The tag number is for later use when a segment must be identified, such as when connecting a voltage source or lumped load to the segment. Any number except zero can be used as a tag. When identify- ing a segment by its tag, the tag number and the number of the segment in the set of segments having that tag are given. Thus, the tag of a segment does not need to be unique. If no need is anticipated to refer back to any segments on a wire by tag, the tag field may be left blank. This results in a tag of zero which cannot be referenced as a valid tag.
- If two wires are electrically connected at their ends, the identical coordinates should be used for the connected ends to ensure that the wires are treated as connected for current interpolation. If wires intersect away from their ends, the point of intersection must occur at segment ends within each wire for interpolation to occur. Generally, wires should intersect only at their ends unless the location of segment ends is accurately known.
- The only significance of differentiating end one from end two of a wire is that the positive reference direction for current will be in the direction from end one to end two on each segment making up the wire.
- As a rule of thumb, segment lengths should be less than 0.1 wave- length at the desired frequency. Somewhat longer segments may be used on long wires with no abrupt changes, while shorter segments, 0.05 wavelength or less, may be required in modeling critical regions of an antenna.
- If input is in units other than meters, then the units must be scaled to meters through the use of a Scale Structure Dimensions (GS) card.
```
> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
