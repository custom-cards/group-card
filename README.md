# Group card

Is a simple card that expands a group to a list of entities to be used with `entities`, `glance`, etc. 

## Installation

Use [HACS](https://hacs.xyz) or follow this [guide](https://github.com/thomasloven/hass-config/wiki/Lovelace-Plugins)

```yaml
resources:
  url: /local/group-card.js
  type: module
```

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:group-card`
| card | object | **Required** | Card object 
| group | string | **Required** | The entity_id of a group
| entities_vars | object | optional | The entity variables depends of card type use and need to have same device_class

Card object

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | A type of card (ex.`glance`) from lovelace
| title | object | optional | Title of the card
| ... | other | optional | Other parameters supported by card type above

Entities vars

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | A type of card (ex.`glance`) from lovelace
| ... | other | optional | Other parameters supported by type above for each entity card 

## Examples

Show all with some exceptions:
```yaml
- type: custom:group-card
  card:
    type: entities
    title: Group card
  group: group.bedroom
```

```yaml
- type: custom:group-card
  card:
    type: vertical-stack
    title: My lights
  group: group.lights
  entities_vars:
    type: light
```

```yaml
- type: custom:group-card
  card:
    type: vertical-stack
    title: Temparatures
  group: group.my_sensors
  entities_vars:
    type: sensor
    graph: line
```

## Credits
- [ciotlosm](https://github.com/ciotlosm)
