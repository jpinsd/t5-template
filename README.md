# t5-template
## Web dev base template with cascading layers and sass

- `npm install` - install all required packages.
- `nvm use 19` - to set NPM to latest (as of this wiritng)
- `npm start` - copies `src` files to `public` and starts Browsersync server at localhost:3000
- `npm run build` - copies files to `public` and autoprefixes/minifies css


## Files
- `sass/utilities/_colors.scss` - sass color variables
- `sass/utilities/_fonts.scss` - font family, and base font styles
- `sass/utilities/_metrics.scss` - breakpoints, padding, animation and transition times
- `sass/components/*.scss` - put individual components in here. Buttons, form elements, etc. Make sure to `@forward` them in `sass/components/index.scss` so they will be included in the output styles. 
- `sass/themes.scss` - dark and light themes, motion and contrast variations.
- `sass/overrides.scss` - anything that needs to be changed from the base styles and components.

Add your own styles anywhere after these. Because we're using cascading `@layer` styles, there should be no need to have to use `!important` anywhere. 

## Notes
To make sure to separate named colors from purpose and function, only use the css variables in `themes.scss`.

```
/* don't do this */
button {
  background: #DF4907;
  color: white;

/* correct */
button {
  background: var(--primary);
  color: var(--on-primary);
}
```



Build scripts are based on the [great work](https://thinkdobecreate.com/articles/minimum-static-site-sass-setup/) by Stephanie Eckles
