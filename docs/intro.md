---
sidebar_position: 0
---
# Getting started

The codebase is built upon several projects below:

- React Native
- Firebase
- React Navigation
- UI Kitten
- TypeScript

## Installation

- In terminal:
  
```console
git clone https://github.com/App-Takeoff/takeoff-web.git
npm i -g expo-cli
```

- Install all dependencies:

```console
cd ./takeoff-web
yarn
```

- `pod-install` to install ios pods

```console
cd ios
npx pod-install
```

- Make sure `react-native.config.js` looks like this:

```js
module.exports = {
  project: {
    ios: {},
    android: {},
  },
  assets: ["./src/assets/fonts"],
}
```

- Run `react-native-link` to link ONLY `assets`
- Known bug when setting up `react-native-vector-icons`:
  - After installing `react-native-vector-icons`, follow [this official docs](https://github.com/oblador/react-native-vector-icons#option-manually)
  - @see [this og solution](https://github.com/react-navigation/react-navigation/issues/6267#issuecomment-528883756)

- Ask @Khoi Tran to provide suitable `.env` file. Add it to the root folder
- To run on web:

`yarn web`

## Running Storybook (Soon)

From the command line in your generated app's root directory, enter `yarn run storybook`
This starts up the storybook server.

In `app/app.tsx`, change `SHOW_STORYBOOK` to `true` and reload the app.

For Visual Studio Code users, there is a handy extension that makes it easy to load Storybook use cases into a running emulator via tapping on items in the editor sidebar. Install the `React Native Storybook` extension by `Orta`, hit `cmd + shift + P` and select "Reconnect Storybook to VSCode". Expand the STORYBOOK section in the sidebar to see all use cases for components that have `.story.tsx` files in their directories.
