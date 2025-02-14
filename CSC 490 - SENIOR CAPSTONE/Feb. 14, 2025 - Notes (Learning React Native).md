# Learning React Native
- Projects for iOS can only be done online and can be sent to your phone that way
- To run a version on your computer you need the command `npx create-expo-app@latest` and the use either:
	 ```shell
	cd my-app
	npm run android
	npm run ios 
	npm run web
	```
- To use iOS on Windows you need to use macOS to build the iOS project - use the Expo app if you need to do iOS development without a Mac

https://reactnative.dev/docs/tutorial
https://expo.dev/accounts/annicamclean


Absolutely! Since you're already familiar with TypeScript, JavaScript, and React, learning React Native will be relatively smooth. React Native leverages your React knowledge but is specifically designed to build mobile apps for iOS and Android using JavaScript (or TypeScript) and React.

Let’s break it down into key topics to help you get started. Here’s a structured roadmap:

### 1. **Setting Up Your Environment**

-   **Node.js** and **npm** or **Yarn** (for managing dependencies)
-   **React Native CLI** or **Expo CLI** (React Native CLI for full flexibility, Expo for easier setup and quicker development).
    -   **Expo** is great for beginners, but using the **React Native CLI** offers more control over native modules.
-   **Android Studio** (for Android development) or **Xcode** (for iOS development) depending on your platform.

You can follow the official [React Native Getting Started](https://reactnative.dev/docs/environment-setup) guide for detailed installation steps.

### 2. **Creating Your First App**

-   Start by initializing your project:
    -   **Using Expo**:
        
        ```bash
        expo init MyFirstApp
        cd MyFirstApp
        expo start
        
        ```
        
    -   **Using React Native CLI**:
        
        ```bash
        npx react-native init MyFirstApp
        cd MyFirstApp
        npx react-native run-android  # Or run-ios
        
        ```
        

Now you have the basic environment ready to run your app on an emulator or real device.

### 3. **Basic React Native Components**

React Native has components that resemble the web components in React, but they have mobile-specific equivalents. For example:

-   `<div>` → `<View>`
-   `<img>` → `<Image>`
-   `<button>` → `<TouchableOpacity>` or `<Button>`
-   `<input>` → `<TextInput>`

Common components to start with:

-   **View**: A container for UI elements, similar to `div`.
-   **Text**: For rendering text, much like React's `Text` component.
-   **Image**: To display images.
-   **TouchableOpacity/TouchableHighlight**: Wrappable components to create interactive buttons.

**Example:**

```tsx
import React from 'react';
import { View, Text, Button, StyleSheet } from 'react-native';

const App = () => {
  return (
    <View style={styles.container}>
      <Text>Hello, React Native!</Text>
      <Button title="Press me" onPress={() => alert('Button pressed!')} />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
});

export default App;

```

### 4. **Styling in React Native**

-   **StyleSheet API**: React Native uses its own `StyleSheet` to handle styles. It’s similar to CSS but written in JavaScript.
-   **Flexbox**: React Native uses Flexbox for layout, just like in the web version of React.

Example of styling:

```tsx
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#fff',
  },
  text: {
    fontSize: 20,
    color: 'blue',
  },
});

```

### 5. **Handling Navigation**

React Native uses libraries like **React Navigation** or **React Native Navigation** to handle navigation between screens.

-   **React Navigation** is the most popular, and it supports **stack navigation**, **tab navigation**, and **drawer navigation**.

You can set it up like this:

```bash
npm install @react-navigation/native
npm install react-native-screens react-native-safe-area-context
npx pod-install ios  # For iOS apps
npm install @react-navigation/stack

```

Example setup:

```tsx
import React from 'react';
import { Button, View, Text } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const HomeScreen = ({ navigation }: any) => (
  <View>
    <Text>Home Screen</Text>
    <Button title="Go to Details" onPress={() => navigation.navigate('Details')} />
  </View>
);

const DetailsScreen = () => (
  <View>
    <Text>Details Screen</Text>
  </View>
);

const Stack = createStackNavigator();

const App = () => (
  <NavigationContainer>
    <Stack.Navigator initialRouteName="Home">
      <Stack.Screen name="Home" component={HomeScreen} />
      <Stack.Screen name="Details" component={DetailsScreen} />
    </Stack.Navigator>
  </NavigationContainer>
);

export default App;

```

### 6. **Using APIs & State Management**

React Native allows you to make API calls and manage state just like you do in React. You can use `fetch` or Axios to interact with RESTful APIs.

For state management:

-   **useState** and **useEffect** work the same way as in React.
-   For complex state, you can use **Context API** or **Redux**.

### 7. **Handling Device Features**

-   React Native has modules to interact with device features like the camera, GPS, etc. These are often provided through third-party libraries such as:
    -   **react-native-camera**
    -   **react-native-location**
-   You can also use **React Native APIs** like `AsyncStorage`, `Clipboard`, or `PushNotificationIOS` for native features.

### 8. **Debugging & Performance**

React Native comes with built-in developer tools:

-   **React Native Debugger** (for inspecting network requests, state, etc.)
-   **Flipper** (advanced debugging tool)
-   **Remote JS Debugging** (using Chrome DevTools)

**Performance optimization**:

-   Use **FlatList** for rendering large lists efficiently.
-   Optimize images using **react-native-fast-image**.

### 9. **Deploying to App Stores**

Once you're ready to deploy your app, React Native allows you to build APKs (for Android) and app bundles or iOS apps. For deployment, you can use:

-   **Expo**: Easier deployment using the Expo app.
-   **React Native CLI**: Manually configuring builds using Xcode/Android Studio.

You'll need to create developer accounts with Google Play and the Apple App Store for publishing.

----------

Does that look like a good overview to start with? Let me know which topic you'd like to dive deeper into!
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MjQ4MTg2MSwyMTM4ODQ4OTA3XX0=
-->