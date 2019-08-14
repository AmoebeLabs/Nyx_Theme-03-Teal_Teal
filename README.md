# Nyx Theme variant #03, Teal/Teal/Teal
A fully dark Teal theme based on Nyx

## What is it
Nyx is an extended night theme, supporting several custom components.
Nyx, the goddess of the night, has a counterpart named Hemera, the goddess of the day.

## Supported Home Assistant and Lovelace components
This theme is build on Home Assistant 0.96.5
It has built-in support for the following custom components:
- The [custom thermostat card](https://github.com/ciotlosm/custom-lovelace/tree/master/thermostat-card)
- The [custom simple weather card](https://github.com/kalkih/simple-weather-card)
- The awesome [custom button card](https://github.com/custom-cards/button-card)
- The great [custom mini graph card](https://github.com/kalkih/mini-graph-card)
- The [custom air visual card](https://github.com/dnguyen800/air-visual-card)

## Simple Preview:
![Nyx 03 Profile](https://github.com/AmoebeLabs/Nyx_Theme-03-Teal_Teal/blob/master/screenshots/nyx-03-profile.png)

## Some real-world screenshots:
![1](https://github.com/AmoebeLabs/Nyx_Theme-03-Teal_Teal/blob/master/screenshots/nyx-03-examples01.png)

![2](https://github.com/AmoebeLabs/Nyx_Theme-03-Teal_Teal/blob/master/screenshots/nyx-03-examples02.png)

## Relation between theme, decluttering templates and views/cards
The theme, templates and cards are related in the sense that the template is using the theme settings, and the cards the template settings, ie: theme --> template --> cards.

Below a light button example for the state "On"

The theme defines the colors:
``` yaml
#
# Entity state = 'on'

theme-button-card-color-state-on:          'rgba(255, 255, 255, 1.0)'
theme-button-area-color-state-on:          'var(--primary-text-color)'
theme-button-icon-color-state-on:          'var(--paper-item-icon-active-color)'
theme-button-label-color-state-on:         'var(--mdc-orange-darken-4)'
theme-button-lock-color-state-on:          'var(--primary-text-color)'
theme-button-name-color-state-on:          'var(--primary-text-color)'
theme-button-state-color-state-on:         'var(--mdc-orange-darken-4)'
```

The template for the custom button-card implements the theme colors/settings for the state "On"

``` yaml
  state:
    - value: "on" 
      spin: '[[spin]]'  
      styles:
        card:
          - --ha-card-background: var(--theme-button-card-color-state-on)
        lock:
          - color: var(--theme-button-lock-color-state-on)
        label:
          - color: var(--theme-button-label-color-state-on)
        name:
          - color: var(--theme-button-name-color-state-on)
        state:
          - color: var(--theme-button-state-color-state-on)
        custom_fields:
          area:
            - color: var(--theme-button-area-color-state-on)
```

The cards need very little yaml code as a result, only functional stuff, NO styling!

``` yaml
          - type: custom:decluttering-card
            template: button_light_template
            variables:
              - entity: light.gledopto
              - area: Woonkamer
              - name: Boekenkast
              - icon: 'mdi:book-open-outline'
```
As a result:
- the cards need very little yaml, and only contain the functional stuff
- the template takes care of defaults and styling
- the theme is the only one responible for the style settings

## Design:
The main colors, based on the [Material Design Color Palettes](https://github.com/AmoebeLabs/Material-Design-Theme-Colors) are:
- Almost Black Teal for backgrounds
- Teal as Primary Color
- Teal as the Secondary Color

## Inspired by...
Of course, I did not re-invent the wheel.
Hemera and Nyx, together with the 3-grid layout and on/off colors are heavily inspred by Apple's HomeKit and the mighty [HomeBridge UI](https://www.npmjs.com/package/homebridge-config-ui-x#accessory-control).

### Homekit:
![](https://github.com/AmoebeLabs/Home-Assistant-Config/blob/master/inspiration/Inspired%20by%20Homekit.png)

### Homebridge:
![](https://github.com/AmoebeLabs/Home-Assistant-Config/blob/master/inspiration/Inspired%20by%20Homebridge.png)

### Last but not least: Google's material design, inclusing design rules:
- https://materializecss.com/color.html
- https://material.io/design/color/#color-usage-palettes
- https://material.io/design/color/dark-theme.html

### And last last but not least: the 3 button topmenu by @jimzz
