# rn-ts-step-by-step
Just a readme file with necessary info to setup React Native project using TypeScript, eslint, prettier and babel

Useful links:
[How to setup RN project with eslint, prettier and etc.](https://dev-yakuza.posstree.com/en/react-native/eslint-prettier-husky-lint-staged/)<br />
[RN project TypeScript template](https://github.com/react-native-community/react-native-template-typescript)

## TODO:
Create React Native app:
```
npx react-native init MyApp --template react-native-template-typescript
```

Install eslint (can be skipped I guess cuz its already is in React Native but w/e):
```
yarn add eslint
```

Configure eslint according to your needs (dont forget to install needed dependencies at the end):
```
npx eslint --init
```

Install prettier and then edit prettier config file (usually .prettierrc.js) according to your needs
```
yarn add prettier eslint-plugin-prettier
```

My preference
```
module.exports = {
  bracketSameLine: true,
  bracketSpacing: true,
  jsxSingleQuote: true,
  trailingComma: "all",
  arrowParens: "avoid",
  printWidth: 100,
  tabWidth: 2,
  semi: true,
};

```

Add Prettier plugin to eslintrc.js
```
plugins: [..., 'prettier'],
rules: {
    ...,
    "prettier/prettier": "error",
  }
```

Add babel module resolver for shorter file paths ([More info here](https://reactnative.dev/docs/typescript#using-custom-path-aliases-with-typescript))
```
yarn add babel-plugin-module-resolver
```

In tsconfig.json file uncomment "baseUrl" and "paths" params and add what you like.
```
"baseUrl": "." /* Base directory to resolve non-absolute module names. */,
"paths": {
  "*": ["src/*"],
  "assets/*": ["src/assets/*"],
  "components/*": ["src/components/*"],
  "constants/*": ["src/constants/*"],
  "screens/*": ["src/screens/*"],
  "utils/*": ["src/utils/*"]
}
```

In babel.config.js add same info as tsconfig.json
```
presets: [...],
plugins: [
    [
      "module-resolver",
      {
        root: ["./src"],
        extensions: [".ios.js", ".android.js", ".js", ".ts", ".tsx", ".json"],
        alias: {
          assets: ["src/assets/*"],
          components: ["src/components/*"],
          constants: ["src/constants/*"],
          screens: ["src/screens/*"],
          utils: ["src/utils/*"],
        },
      },
    ],
  ],
```
