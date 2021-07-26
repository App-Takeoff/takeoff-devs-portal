---
sidebar_position: 1
---
# Overview

The App Takeoff project's structure will look similar to this:

```js
takeoff-web
├── src
│   ├── screens
│   ├── assets
│   ├── utils
│   ├── components
│   ├── engines
├── storybook @soon
│   ├── views
│   ├── index.ts
│   ├── storybook-registry.ts
│   ├── storybook.ts
├── test @soon
│   ├── __snapshots__
│   ├── storyshots.test.ts.snap
│   ├── mock-i18n.ts
│   ├── mock-reactotron.ts
│   ├── setup.ts
│   ├── storyshots.test.ts
├── README.md
├── android
├── ios
├── .env
└── package.json

```

## Folder structure

> SAUCE stands for: `Screens - Assets - Utils - Components - Engines`

The inside of the src directory looks similar to the following:

```java
app
├── screens
    |_ _navigation - This is where your `react-navigation` navigators will live
├── assets
    |_ fonts*
    |_ images
    |_ svg*
    |_ icons
├── utils 💩
    |_ styles - Styles, color, theme, etc.
    |_ storage - Everything related to AsS (Async Storage, but i like what u think)
    |_ helpers - Useful values for the codebase (scaling, device-related values... )
    |_ i18n* - Translation setup, with `react-native-i18n`
    |_ errors -  Pre-defined error code
    |_ typings - Type annotations in TypeScript
├── components
├── engines
    |_ functions - complex js functions, grouped by functionalities, that help us do the job
    |_ backends - Backends handlers
    |_ firebase - FRBS-related callable functions
    |_ hooks - custom hooks functions are built here
    |_ providers - React-Context providers; think of it like a global state management
```

## ./storybook directory

This is where your stories will be registered and where the Storybook configs will live

## ./test directory

This directory will hold your Jest configs and mocks, as well as your [storyshots](https://github.com/storybooks/storybook/tree/master/addons/storyshots) test file. This is a file that contains the snapshots of all your component storybooks.

## Running Storybook (Soon)

From the command line in your generated app's root directory, enter `yarn run storybook`
This starts up the storybook server.

In `app/app.tsx`, change `SHOW_STORYBOOK` to `true` and reload the app.

For Visual Studio Code users, there is a handy extension that makes it easy to load Storybook use cases into a running emulator via tapping on items in the editor sidebar. Install the `React Native Storybook` extension by `Orta`, hit `cmd + shift + P` and select "Reconnect Storybook to VSCode". Expand the STORYBOOK section in the sidebar to see all use cases for components that have `.story.tsx` files in their directories.


## react-native-firebase@5.6.0

There --is-- maybe a problem with "Sign in with Apple" -related thing.

```
~~/primr-web/node_modules/react-native-firebase/ios/RNFirebase/auth/RNFirebaseAuth.m:1184:36: No known class method for selector 'credentialWithProviderID:IDToken:rawNonce:'

```

Temporary solutions: Inside `RNFirebaseAuth.m`, remove the line

```
else if ([provider compare:@"apple.com" options:NSCaseInsensitiveSearch] == NSOrderedSame) {
    credential = [FIROAuthProvider credentialWithProviderID:@"apple.com" IDToken:authToken rawNonce:authTokenSecret];
  }

```

(Access `RNFirebaseAuth.m` thru clicking the error above)
