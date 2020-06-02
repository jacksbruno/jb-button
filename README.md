# jb-button
 > Button component based on vuejs

## Installation

` yarn add jb-button `

## Basic Usage
>Use `format` and `type` to define Button`s style.

![](https://github.com/jacksbruno/jb-button/blob/master/src/assets/simple-buttons.jpg)

``` javascript
<div class="row">
  <jb-button title="Plain" format="plain"/>
  <jb-button title="Plain" format="plain" type="primary" />
  <jb-button title="Plain" format="plain" type="success"/>
  <jb-button title="Plain" format="plain" type="success"/>
</div>

<div class="row">
  <jb-button title="Round" />
  <jb-button title="Round" type="primary" />
  <jb-button title="Round" type="success"/>
  <jb-button title="Round" type="success"/>
</div>

<div class="row">
  <jb-button title="Circle" prefix/>
    <img src="@/assets/settings.svg" slot="prefix" />
  </jb-button>
  <jb-button title="Circle" type="primary" prefix />
    <img src="@/assets/settings_branco.svg" slot="prefix" />
  <jb-button>
  <jb-button title="Circle" type="success" prefix />
    <img src="@/assets/settings_branco.svg" slot="prefix" />
  </jb-button>
  <jb-button title="Circle" type="success" prefix />
    <img src="@/assets/settings_branco.svg" slot="prefix" />
  </jb-button>
</div>
```

## Size Button
> Besides default size, Button component provides three additional sizes for you to choose among different scenarios.

![](https://github.com/jacksbruno/jb-button/blob/master/src/assets/size-buttons.jpg)

``` javascript
<div class="row">
  <jb-button title="Plain" format="plain" size="large" />
  <jb-button title="Plain" format="plain" size="medium" />
  <jb-button title="Plain" format="plain" size="small" />
  <jb-button title="Plain" format="plain" size="mini" />
</div>
```

## Disabled Button
> The `disabled` attribute determines if the button is disabled.

![](https://github.com/jacksbruno/jb-button/blob/master/src/assets/disabled-buttons.jpg)

``` javascript
<div class="row">
  <jb-button title="Default" format="plain" disabled />
  <jb-button title="Primary" format="plain" disabled />
  <jb-button title="Success" format="plain" disabled />
  <jb-button title="Danger" format="plain" disabled />
</div>
```

## Icon Button
> Use `icons` or `svg` to add more meaning to Button. You can use icon alone to save some space, or use it with text.

![](https://github.com/jacksbruno/jb-button/blob/master/src/assets/icons-buttons.jpg)

``` javascript
<div class="row">
  <jb-button format="plain" type="primary" prefix>
    <img src="@/assets/settings_branco.svg" slot="prefix" />
  </jb-button>
  <jb-button format="plain" type="primary" sufix>
    <img src="@/assets/settings_branco.svg" slot="sufix" />
  </jb-button>
  <jb-button format="plain" type="primary" disabled>
    <img src="@/assets/settings_branco.svg" slot="prefix" />
    <label slot="sufix">Icon Prefix</label>
  </jb-button>
  <jb-button format="plain" type="primary" disabled>
    <img src="@/assets/settings_branco.svg" slot="sufix" />
    <label slot="prefix">Icon Sufix</label>
  </jb-button>
</div>
```

## Attributes
| Attribute  | Description  | Type | Accepted values | Default
| :------------ |:---------------|:-----:|:-----------:|:----------:|
| title    | some title for the button | string | -- | -- |
| size    | button size | string | large / medium / small / mini | medium |
| type    | button type | string | default / primary / success / danger | default |
| format    | determine the shape of the button | string | plain / round / circle | round |
| prefix    | used when there is an icon on the Button | boolean | -- | false |
| sufix    | used in conjunction with the prefix attribute to add a label / icon / svg to the Button | boolean | -- | false |
| expandLeft    | this attribute defines which way the hover animation opens the Button, left or right | boolean | -- | true |
| disabled    | disable the button | boolean | -- | false |
| loader    | determine whether it`s loading | boolean | -- | false |

## Slots
| Name  | Description  |
| :------------ |:---------------|
| prefix    | It is used to add an icon, svg or text, it may or may not be used in conjunction with the sufix slot. When using text, it is advisable to use a `label` tag. This slot will always be left aligned. |
| sufix    | It is used to add an icon, svg or text, it may or may not be used in conjunction with the prefix slot. When using text, it is advisable to use a `label` tag. This slot will always be aligned to the right. |

# End
