# jb-button
 > Button component based on vuejs

## Installation

` yarn add gp-button `

## Basic Usage
>Use `format` and `type` to define Button`s style.

![](data:image/png;base64,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)

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

![](data:image/png;base64,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)

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

![](data:image/png;base64,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)

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

![](data:image/png;base64,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)

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
| title    | some wordy text | string | -- | -- |
| size    | button size | string | large / medium / small / mini | medium |
| type    | button type | string | default / primary / success / danger | default |
| format    | determine the shape of the button | string | plain / round / circle | round |
| prefix    | used when there is an icon on the Button | boolean | -- | false |
| sufix    | used in conjunction with the prefix attribute to add a label / icon / svg to the Button | boolean | -- | false |
| expandLeft    | this attribute defines which way the hover animation opens the Button, left or right | boolean | -- | true |
| disabled    | disable the button | boolean | -- | false |
| loader    | determine whether it`s loading | boolean | -- | false |

#End