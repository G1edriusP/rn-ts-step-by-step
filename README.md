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

Install prettier
```
yarn add prettier eslint-plugin-prettier
```

Add Prettier plugin to eslintrc.js
```
plugins: [..., 'prettier'],
rules: {
    ...,
    "prettier/prettier": "error",
  }
```
