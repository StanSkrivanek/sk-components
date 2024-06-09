# Stans Svelte Components lib

## Elements

### Badges

[x] - basic

[] - basic Switch
[x] - Pill
[x] - with ON-OFF label on right
[x] - with ON-OFF text in thumb
[ ] - with Icons in thumb

### Button

[x] Basic `<button>`
[ ] Basic `<a>`

| attribute  | description                                                                                  |
| ---------- | -------------------------------------------------------------------------------------------- |
| `is`       | is used to add classes like "color", "size", "shape", "type", "disabled", "block", "outline" |
| `disabled` | button will be disabled                                                                      |
| `onclick`  | button click event method                                                                    |

| `is`      | values                                                                                  | description                                                                   |
| --------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **color** | `primary`, `secondary`, `success`, `danger`, `warning`, `info`, `light`, `dark`, `link` | basic colors                                                                  |
| **size**  | `xs`, `sm`, `md`, `lg`                                                                  | basic sizes if not set the button has init values                             |
| **shape** | `pill`, `rounded`, `outline`                                                            | button shapes                                                                 |
| **block** | `block`                                                                                 | set button as `block` element, if not set the button is an **inline** element |

```html
<BtnSwitchBasic is="outline lg red pill block">Primary</BtnSwitchBasic>
```

### Checkbox

HTML input `type="checkbox"` has `checked | unchecked` states defined by default and `indeterminate` for group of checkboxes. The `role="switch"` is not necessary, but it can be used to determine that checkbox is used as a switch. The `aria-checked` attribute is used to determine the state of the switch.

<!-- table with buttons
[x] - primary
[x] - secondary
[x] - success
[x] - danger
[x] - warning
[x] - info
[x] - light
[x] - dark
[x] - link -->

## TODO

- **Forms**
  - Inputs (single, group with Icon etc)
  - Checkbox (single, group) **(group = $bindable())** doesn't work in svelte 5 yet as getting errors and RH says it not priority yet [github](https://github.com/sveltejs/svelte/pull/11256)
  - Radio
  - Calendar
  - Select
- **UI**
  - Tooltips
  - Toasts
  - Pagination
  - Tabs
  - Avatars
  - Navigations

## Components

- Modal
- Dialog
