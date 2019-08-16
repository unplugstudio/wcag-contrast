# WCAG Contrast [![Build Status](https://travis-ci.com/unplugstudio/wcag-contrast.svg?branch=master)](https://travis-ci.com/unplugstudio/wcag-contrast)

> Utilities to work with WCAG color contrast

## Install

```
$ npm install wcag-contrast
```

## Sass

<a id="general-function-luminance"></a>

### @function luminance

Determine the luminance of a color (between 0 and 1) according to the WCAG algorithm

+ **Group:** General
+ **Access:** public

#### Parameters

| Name     | Type                                                           | Description | Default |
| :------- | :------------------------------------------------------------- | :---------- | :------ |
| `$color` | **[Color](https://sass-lang.com/documentation/values/colors)** | Color       | -       |

#### Returns

**[Number](https://sass-lang.com/documentation/values/numbers)** Luminance: 1 is pure white, 0 is pure black

#### Dependents

+ **@function contrast** Calculate the contrast ratio between two colors
+ **@function contrast** Calculate the contrast ratio between two colors

#### Links

+ <https://css-tricks.com/snippets/sass/luminance-color-function/>
+ <http://www.w3.org/TR/2008/REC-WCAG20-20081211/#relativeluminancedef>

<a id="general-function-contrast"></a>

### @function contrast

Calculate the contrast ratio between two colors

+ **Group:** General
+ **Access:** public

#### Parameters

| Name     | Type                                                           | Description             | Default |
| :------- | :------------------------------------------------------------- | :---------------------- | :------ |
| `$back`  | **[Color](https://sass-lang.com/documentation/values/colors)** | Background color        | -       |
| `$front` | **[Color](https://sass-lang.com/documentation/values/colors)** | Foreground (text) color | -       |

#### Returns

**[Number](https://sass-lang.com/documentation/values/numbers)** The relative contrast of both colors

#### Dependencies

+ **[@function luminance](#general-function-luminance)**
+ **[@function luminance](#general-function-luminance)**

#### Dependents

+ **@function choose-contrast-color** Determine whether to use dark or light text on top of given color
+ **@function choose-contrast-color** Determine whether to use dark or light text on top of given color

#### Links

+ <https://www.w3.org/TR/2008/REC-WCAG20-20081211/#contrast-ratiodef>

<a id="general-function-choose-contrast-color"></a>

### @function choose-contrast-color

Determine whether to use dark or light text on top of given color

+ **Group:** General
+ **Access:** public

#### Parameters

| Name            | Type                                                               | Description                                                 | Default |
| :-------------- | :----------------------------------------------------------------- | :---------------------------------------------------------- | :------ |
| `$color`        | **[Color](https://sass-lang.com/documentation/values/colors)**     | Background color                                            | -       |
| `$contrast`     | **[Number](https://sass-lang.com/documentation/values/numbers)**   | How much contrast is considered enough                      | `4.5`   |
| `$prefer-white` | **[Boolean](https://sass-lang.com/documentation/values/booleans)** | Prefer white when both black and white have enough contrast | `true`  |

#### Returns

**[Color](https://sass-lang.com/documentation/values/colors)** #fff or #000

#### Dependencies

+ **[@function contrast](#general-function-contrast)**
+ **[@function contrast](#general-function-contrast)**

#### Links

+ <https://www.w3.org/WAI/WCAG21/Techniques/general/G18.html>
