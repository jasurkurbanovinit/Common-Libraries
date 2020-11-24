# Common-Libraries
## Navigation (Stack )

```bash
  yarn add @react-navigation/native yarn add @react-navigation/stack react-native-reanimated react-native-gesture-handler react-native-screens react-native-safe-area-context @react-native-community/masked-view
```

To finalize installation of react-native-gesture-handler, add the following at the top (make sure it's at the top and there's nothing else before it) of your entry file, such as ```index.js``` or ```App.js```:

```bash import 'react-native-gesture-handler';
import * as React from 'react';
import { NavigationContainer } from '@react-navigation/native';

export default function App() {
  return (
    <NavigationContainer>{/* Rest of your app code */}</NavigationContainer>
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
