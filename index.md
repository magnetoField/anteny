---
layout: default
---
# Równania Maxwella

| Postać różniczkowa | Postać całkowa | Sens fizyczny równania |
| :---: | :---: | :--- |
| $\nabla \times \vec{E} = -\frac{\partial \vec{B}} {\partial {t}}$ | $\oint\limits_L \vec{E} \cdot \text{d}\vec{l} = -\frac{\text{d}\Phi_B}{\text{d}t}$ <br /> gdzie $\Phi_B$ – strumień magnetyczny przez dowolny kontur rozpięty na krzywej L | Zmienne w czasie pole magnetyczne wytwarza pole elektryczne. |
| $\nabla \times \vec{B} = \mu \vec{j} +\mu \varepsilon \frac{\partial \vec{E}} {\partial {t}}$ | $\oint\limits_L \vec{B} \cdot \text{d}\vec{l} = \mu I + \mu \varepsilon \frac{\text{d}\Phi_E}{\text{d}t}$ <br /> gdzie $\Phi_E$ – strumień elektryczny przez dowolny kontur rozpięty na krzywej L, a $I$ – całkowity prąd elektryczny przecinający ten kontur | Przepływający prąd oraz zmienne pole elektryczne wytwarzają pole magnetyczne. |
| $\varepsilon \nabla \cdot \vec{E} = \rho$ | $\varepsilon \oint\limits_S \vec{E} \cdot \text{d}\vec{S} = q$ <br /> gdzie $q$ – całkowity ładunek zawarty wewnątrz powierzchni $S$ | Ładunki są źródłem pola elektrycznego. |
| $\nabla \cdot \vec{B} = 0$ | $\oint\limits_S \vec{B} \cdot \text{d}\vec{S} = 0$ | Pole magnetyczne jest bezźródłowe. |

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

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
