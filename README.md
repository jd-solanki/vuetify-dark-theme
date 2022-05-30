# vuetify-dark-theme

## Issue we can't set dark theme's primary color using `setTheme`

```js
const setPrimaryColor = color => {
  console.log("Color: ", color)
  themes.value.light.colors.primary = color
  themes.value.dark.colors.primary = color

  setTheme('light', themes.value.light)
  setTheme('dark', themes.value.dark)
}
```

## Steps

1. Run the project
2. Click on "primary" button to change the primary color to black _(You will notice button color updated to black)_
3. Click on icon button to switch theme to dark _(Color is still the same)_