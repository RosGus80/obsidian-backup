
Native AsyncStorage lib is deprecated and no longer used, but there is a community lib that provides the same utility. It is @react-native-async-storage/async-storage.
`npx expo install @react-native-async-storage/async-storage`

It just stores the dictionary with key-value data on the user's device. You can set items, remove them, and do anything you want with it. And it will be executed asynchronously!!
```
import AsyncStorage from "@react-native-async-storage/async-storage";


export default function Main() {

	const [profile] = useAtom(profileAtom);

  

	useEffect(() => {

AsyncStorage.setItem('me', "Rostislav").then(async () => {

console.log(await AsyncStorage.getAllKeys()); 
console.log(await AsyncStorage.getItem('me'));
});

}, []);

```