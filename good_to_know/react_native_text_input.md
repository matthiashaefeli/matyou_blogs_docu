# Text input field with react native

state:
```
const [value, setValue] = useState('')
```

input field:

```
<TextInput
  style={styles.text}
  autoCapitalize='none'
  autoCorrect={false}
  value={value}
  onChangeText={ (text) => setValue(text) }
/>
```

styles:
```
const styles = StyleSheet.create({
  input: {
    margin: 15,
    borderColor: 'black',
    borderWidth: 1
  }
});
```

