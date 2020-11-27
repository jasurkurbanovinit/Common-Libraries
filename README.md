# React Native Most Used Libraries 
## Navigation (Stack)
## Install
```bash
yarn add @react-navigation/native yarn add @react-navigation/stack react-native-reanimated react-native-gesture-handler react-native-screens react-native-safe-area-context @react-native-community/masked-view
```

```bash
yarn add @react-navigation/bottom-tabs
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

## Stack Navigation Demo
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
