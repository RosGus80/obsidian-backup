
```
import { StatusBar } from 'expo-status-bar';
import { StyleSheet, Text, TextInput, Button, View } from 'react-native';

export default function App() {
	return (
	<View style={{height: 300, justifyContent: "space-evenly", alignItems: "center", flexDirection: "row", backgroundColor: "crimson"}}>
		<View style={{width: 100, height: 100, backgroundColor: "powderblue"}}></View>
		<View style={{width: 100, height: 100, backgroundColor: "lightblue", alignSelf: "flex-start"}}></View>
		<View style={{width: 100, height: 100, backgroundColor: "steelblue"}}></View>
	</View>
);

}

```

flex-direction just flips the axis (by default (flex-column) main axis is vertical, nut in flex-row it becomes horizontal). Align-items sets the position on the second axis, which has different directions depending on flex-direction. So in flex-column align-items sets the position horizontally but on flex-row it sets position vertically