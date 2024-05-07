In React Native, logical AND may cause crash as below.

[Conditional rendering in React Native may crash your app](https://www.koprowski.it/blog/conditional-rendering-react-native-text-crash/)

This babel plugin [here](https://gist.github.com/bogas04/d27ec339ff48758525bb4ca3136367cb) can replace all logical AND with ternary operators, with a little more configuration.

```jsx
// .babelrc.js
module.exports = function (api) {
    api.cache(true);

    const presets = [];
    const plugins = [
        './ternary-jsx.js',
// this two plugins below only parse but not transform code
        ['@babel/plugin-syntax-decorators', { decoratorsBeforeExport: true }],
        ['@babel/plugin-syntax-class-properties', { loose: true }],
    ];

    return {
        parserOpts: {
            plugins: ['jsx', 'typescript'],
        },
        presets,
        plugins,
        generatorOpts: {
            retainLines: true,
            compact: false,
            minified: false,
            concise: false,
        },
    };
};
```

However, [babel will lost all code foramt and cause too much meaningless change](https://stackoverflow.com/questions/77531610/how-to-prevent-babel-from-formatting-the-generated-code).


