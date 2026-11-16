Watchers are functions that let us call a callback each time our reactive state changes. It calls a callback if the "dependencies"- vars that are defined as triggers - are changed. Example:
```
watch(dep, () => {
	console.log(dep);
})
```

It waits for the dep var to change and then prints it out. Also we can pass a list of vars to call our callback whenever any of them change:
```
watch([dep1, dep2], () => {
	console.log('Wathcer called!');
})
```

Also we can pass new and old values into callback args so that we can operate with them:

```
watch(dep, (oldValue, newValue) => {
	console.log(oldValue - newValue);
}
```

Note that the dependencies shall be reactive or it would cause an undefined behaviour

If we have multiple dependencies as a list, oldValue and newValue would be arrays of these dependencies (indexed in order from the list):
```
watch([justForItToBe, totalExpense], (newValue, oldValue) => {
	console.log(oldValue);
	console.log(newValue);
});
```

```
Array (2)
0: 0
1: 100
```

Watcher may take the third argument and it would define if a watcher is immediate or be only called once:

```
watch(dep, () => {
	console.log(dep);
}, { once: true })
```

or

```
watch(dep, () => {
	console.log(dep);
}, { immediate: true })
```


A shortcut for writing watchers would be the watchEffect function. It just needs to have a defined callback and would make all the variables that are used there its dependencies:

```
watchEffect(() => {
	console.log(futureDep);
	console.log(newFutureDep);
})
```


https://ru.vuejs.org/guide/essentials/watchers