# antd-theme-webpack-plugin

This webpack plugin is to  generate color specific less/css and inject into your `index.html` file so 
that you can change Ant Design specific color theme in browser.

Live Theme Demo: https://mzohaibqc.github.io/antd-live-theme/

In order to integrate with your webpack configurations, install the package and add following code in your webpack config file.

```js
const AntDesignThemePlugin = require('antd-theme-webpack-plugin');

const options = {
  stylesDir: path.join(__dirname, './src/styles'),
  antDir: path.join(__dirname, './node_modules/antd'),
  varFile: path.join(__dirname, './src/styles/variables.less'),
  mainLessFile: path.join(__dirname, '../../src/styles/index.less'),
  themeVariables: ['@primary-color'],
  indexFileName: 'index.html'
}

const themePlugin = new AntDesignThemePlugin(options);
// in config object
plugins: [
    themePlugin
  ]
```
Add this plugin in `plugins` array.

- Here are some default paths.
- Default html file name
  - index.html
- Styles directory default path
  - /src/styles
- Ant Design deafult path
  - /node_modules/antd
- Default variables file path
  - /src/styles/variables.less
- Default styles main file path
  - /src/styles/index.less
- Default Theme variables (that can be updated in browser)
  - ['@primary-color']

So if your directory structure is different or file names are different then provide correct paths as options 
while initailizing plugin

If you directory structure is same as below then you don't need to override path
```
/
  /src
    /styles
      /index.less
      /variables.less
      /otherlessfiles.less
  node_modules
  public/index.html (index.html file at any path, only name matters in this case)
```
