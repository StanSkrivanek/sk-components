# [Switch Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/switch/)

A `switch` is an input widget that allows users to choose one of two values: **on** or **off**. Switches are similar to `checkboxes` and `toggle buttons`, which can also serve as binary inputs. **One difference**, however, is that **switches** can only be used for **binary _(two values)_** input while **checkboxes and toggle buttons** allow implementations the option of supporting a **third middle state**.

Checkboxes can be checked or not checked and can optionally also allow for a partially checked state. Toggle buttons can be pressed or not pressed and can optionally allow for a partially pressed state.

Since **switch, checkbox, and toggle** button all offer binary input, they **are** often functionally **interchangeable**. **Choose the role that best matches both the visual design and semantics of the user interface**. For instance, there are some circumstances where the semantics of on or off would be easier for assistive technology users to understand than the semantics of checked or unchecked, and vice versa. Consider a widget for turning lights on or off. In this case, screen reader output of Lights switch on is more user friendly than Lights checkbox checked. However, if the same input were in a group of inputs labeled Which of the following must be included in your pre-takeoff procedures?, Lights checkbox checked would make more sense.

## Switch Button | [type="button"] | role="switch"

[W3C](https://www.w3.org/WAI/ARIA/apg/patterns/switch/examples/switch-button/)
The role `switch` determine that button can be used as a switch between two states.

```html
<button type="button" role="switch" aria-checked="false" aria-label="Switch">
	<span aria-hidden="true">OFF</span>
	<span aria-hidden="true">ON</span>
	<span class="switch__thumb"></span>
</button>
```

## Switch Input | [type="checkbox"]

[W3C](https://www.w3.org/WAI/ARIA/apg/patterns/switch/examples/switch-checkbox/)
THe checkbox has implemented `checked | unchecked` state. The `role="switch"` is not necessary, but it can be used to determine that checkbox is used as a switch.

``` html
<input type="checkbox" role="switch" aria-label="Switch" >
```

## Switch HTML element | role="switch"

[W3C](https://www.w3.org/WAI/ARIA/apg/patterns/switch/examples/switch-element/)
The `role="switch"` is used to determine that the element is used as a switch. The `aria-checked` attribute is used to determine the state of the switch.

``` html
<div role="switch" aria-checked="false" tabindex="0">
  <span class="label">Notifications</span>
  <span class="switch">
    <span></span>
  </span>
  <span class="on" aria-hidden="true">On</span>
  <span class="off" aria-hidden="true">Off</span>
</div>
```
