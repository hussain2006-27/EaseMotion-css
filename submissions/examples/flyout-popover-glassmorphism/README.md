# EaseMotion Flyout Popover (Glassmorphism)

A pure CSS, JavaScript-free dynamic flyout popover menu, crafted with a modern frosted-glass aesthetic. It perfectly overlays complex backgrounds, allowing colors and shapes to blur dynamically through the menu UI.

## Features
- **Zero JS Dependencies:** Operates natively in the browser via the hidden checkbox hack (`:checked`). Includes a pure CSS invisible full-screen overlay to handle "click outside to close" behavior.
- **Glassmorphism Design:** Employs `backdrop-filter: blur`, highly calibrated translucent `rgba()` backgrounds, and crisp 1px semi-transparent borders to create a premium glass effect.
- **Responsive Shape-Shifting:** On desktop and tablet, it operates as an anchored dropdown. On mobile viewports (`< 600px`), it seamlessly unhooks and transforms into a floating bottom-centered modal to ensure perfect tap targets on small screens.
- **Hardware-Accelerated Transitions:** Employs `transform: scale` and `translateY` for buttery smooth entrance and exit animations.
- **Accessible:** Includes appropriate `role="button"`, `aria-haspopup`, custom focus states bypassing default blue rings, and native support for `prefers-reduced-motion`.

## Usage

Structure your popover precisely as follows:

1. Wrap the module in `<div class="em-flyout-wrapper">`.
2. Place the state-managing `<input type="checkbox">` first.
3. Add the `<label class="em-flyout-overlay">` immediately after it (this handles closing).
4. Add the trigger `<label>`.
5. Add the `.em-flyout-menu` containing the popover contents.

```html
<div class="em-flyout-wrapper">
  <!-- 1. State Manager -->
  <input type="checkbox" id="glass-popover" class="em-flyout-toggle" aria-hidden="true" />
  
  <!-- 2. Close Overlay -->
  <label for="glass-popover" class="em-flyout-overlay" tabindex="-1"></label>
  
  <!-- 3. Trigger -->
  <label for="glass-popover" class="em-btn-glass" tabindex="0" role="button">
    Actions
  </label>
  
  <!-- 4. Flyout Content -->
  <div class="em-flyout-menu">
    <ul class="em-menu-list">...</ul>
  </div>
</div>
