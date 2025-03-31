## Switches

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Switch Buttons</title>
    <style>
      :root {
        --switch-width: 60px;
        --switch-height: 34px;
        --switch-bg-color: #ddd;
        --switch-checked-bg-color: maroon;
        --switch-handle-color: #fff;
        --switch-handle-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
        --switch-transition: 0.3s ease-in-out;
      }

      *,
      ::before,
      ::after {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-family: Arial, sans-serif;
        background: #f4f4f4;
      }

      .switch-container {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 40px;
      }

      .switch {
        position: relative;
        display: inline-flex;
        width: var(--switch-width);
        height: var(--switch-height);
        align-items: center;
        cursor: pointer;
      }

      .switch-input {
        display: none;
      }

      .switch-bg {
        width: 100%;
        height: 100%;
        background: var(--switch-bg-color);
        border-radius: calc(var(--switch-height) / 2);
        transition: background-color var(--switch-transition), box-shadow 0.3s
            ease-in-out;
      }

      .switch-handle {
        position: absolute;
        top: 4px;
        left: 4px;
        width: calc(var(--switch-height) - 8px);
        height: calc(var(--switch-height) - 8px);
        background: var(--switch-handle-color);
        border-radius: 50%;
        box-shadow: var(--switch-handle-shadow);
        transition: transform var(--switch-transition), box-shadow 0.3s
            ease-in-out;
      }

      /* Use transform instead of left */
      .switch-input:checked ~ .switch-handle {
        transform: translateX(calc(var(--switch-width) - var(--switch-height)));
      }

      .switch-input:checked + .switch-bg {
        background-color: var(--switch-checked-bg-color);
        box-shadow: 0px 0px 10px rgba(128, 0, 0, 0.5);
        /* Subtle glow effect */
      }

      .switch-input:checked ~ .switch-handle {
        box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
      }

      /* Accessibility: Focus outline */
      .switch-input:focus-visible + .switch-bg {
        outline: 2px solid #000;
        outline-offset: 2px;
      }
    </style>
  </head>

  <body>
    <div class="switch-container">
      <label class="switch" role="switch" aria-checked="false">
        <input type="checkbox" class="switch-input" aria-label="Switch 1" />
        <span class="switch-bg"></span>
        <span class="switch-handle"></span>
      </label>
      <label class="switch" role="switch" aria-checked="false">
        <input type="checkbox" class="switch-input" aria-label="Switch 2" />
        <span class="switch-bg"></span>
        <span class="switch-handle"></span>
      </label>
      <label class="switch" role="switch" aria-checked="false">
        <input type="checkbox" class="switch-input" aria-label="Switch 3" />
        <span class="switch-bg"></span>
        <span class="switch-handle"></span>
      </label>
    </div>
  </body>
</html>
```
