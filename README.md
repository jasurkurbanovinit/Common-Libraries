# React Native Most Used Libraries 
## Navigation (Stack)
## Install
```bash
yarn add @react-navigation/native yarn add @react-navigation/stack react-native-reanimated react-native-gesture-handler react-native-screens react-native-safe-area-context @react-native-community/masked-view
```

```bash
yarn add @react-navigation/bottom-tabs
```

# Material Top Tabs 
```bash
yarn add @react-navigation/material-top-tabs react-native-tab-view
```

# Getting Started with TypeScript

You can use the TypeScript template:

```bash
npx react-native init MyApp --template react-native-template-typescript
```

# Add Typescript To Existing Project 
## 1) Add TypeScript and the types for React Native and Jest to your project.
```bash
yarn add -D typescript @types/jest @types/react @types/react-native @types/react-test-renderer
```

## 2) Add a TypeScript config file. Create a `tsconfig.json` in the root of your project:
```bash
{
  "compilerOptions": {
    "allowJs": true,
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "isolatedModules": true,
    "jsx": "react",
    "lib": ["es6"],
    "moduleResolution": "node",
    "noEmit": true,
    "strict": true,
    "target": "esnext"
  },
  "exclude": [
    "node_modules",
    "babel.config.js",
    "metro.config.js",
    "jest.config.js"
  ]
}
```

## 3) Create a `jest.config.js` file to configure Jest to use TypeScript
```bash
module.exports = {
  preset: 'react-native',
  moduleFileExtensions: ['ts', 'tsx', 'js', 'jsx', 'json', 'node']
};
```

## 4) Rename a JavaScript file to be `*.tsx`.
For example App.tsx
*You should leave the `./index.js` entrypoint file as it is otherwise you may run into an issue when it comes to bundling a production build.*

## 5) Run `yarn tsc` to type-check your new TypeScript files.

# Install Firebase To React Native Project
```bash
# Using npm
npm install --save @react-native-firebase/app

# Using Yarn
yarn add @react-native-firebase/app
```
*The `@react-native-firebase/app` module must be installed before using any other Firebase service.*

## Android Setup
On the Firebase console, add a new Android application and enter your projects details. The "Android package name" must match your local projects package name which can be found inside of the manifest tag within the `/android/app/src/main/AndroidManifest.xml` file within your project.

### Generating Android credentials

The debug signing certificate is optional to use Firebase with your app, but is required for Dynamic Links, Invites and Phone Authentication. 
To generate a certificate run 
```bash 
 cd androidx && ./gradlew signingReport 
```
and copy the SHA1 from the debug key. This generates two variant keys. You can copy the `'SHA1'` that belongs to the `debugAndroidTest` variant key option.

Download the `google-services.json` file and place it inside of your project at the following location: `/android/app/google-services.json`.

## Configure Firebase with Android credentials

To allow Firebase on Android to use the credentials, the `google-services` plugin must be enabled on the project. 
This requires modification to two files in the Android directory.

First, add the `google-services` plugin as a dependency inside of your `/android/build.gradle file`:
```bash
buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms:google-services:4.3.3' // Add this line ---
  }
}
```

To finalize installation of react-native-gesture-handler, add the following at the top (make sure it's at the top and there's nothing else before it) of your entry file, such as ```index.js``` or ```App.js```:

```bash 
import 'react-native-gesture-handler';
import * as React from 'react';
import { NavigationContainer } from '@react-navigation/native';

export default function App() {
  return (
    <NavigationContainer>{/* Rest of your app code */}</NavigationContainer>
  );
}

```

## Stack Navigation Minimal Example
```bash 
// In App.js in a new project
import * as React from 'react';
import { View, Text } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

function HomeScreen() {
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Home Screen</Text>
    </View>
  );
}

const Stack = createStackNavigator();

function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

export default App;
```

## Minimal example of tab-based navigation

```bash
import * as React from 'react';
import { Text, View } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';

function HomeScreen() {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Home!</Text>
    </View>
  );
}

function SettingsScreen() {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Settings!</Text>
    </View>
  );
}

const Tab = createBottomTabNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Tab.Navigator>
        <Tab.Screen name="Home" component={HomeScreen} />
        <Tab.Screen name="Settings" component={SettingsScreen} />
      </Tab.Navigator>
    </NavigationContainer>
  );
}
```

Link - https://reactnavigation.org/docs/hello-react-navigation/

#### Icons

Link - https://github.com/oblador/react-native-vector-icons

```bash
yarn add react-native-vector-icons
```
then
```bash
react-native link react-native-vector-icons
```
