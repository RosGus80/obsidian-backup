
`npm install react-native-keyboard-accessory`

```

import { KeyboardAccessoryView } from 'react-native-keyboard-accessory'
import { Keyboard, TextInput, View, Button } from 'react-native'
import { useState } from 'react'

export default function YourScreen() {
  const [text, setText] = useState('')

  return (
    <>
      <TextInput
        value={text}
        onChangeText={setText}
        style={{ height: 40, borderBottomWidth: 1, margin: 20 }}
      />

      <KeyboardAccessoryView alwaysVisible>
        <View style={{ flexDirection: 'row', justifyContent: 'flex-end', padding: 10 }}>
          <Button title="Done" onPress={() => Keyboard.dismiss()} />
        </View>
      </KeyboardAccessoryView>
    </>
  )
}
```
