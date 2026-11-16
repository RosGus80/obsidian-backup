
We can add custom directives in Vue using three different ways:

Custom directives (and directives in general) are ought to be used only if some **action can only be done via dom manipulation**

1) In script setup define an object which name starts with v:
   ```
	const vHighlight = {
		mounted: (el) => {
			el.classList.add('focused');
		}
	}
	```
2) Outside of setup:
```
export default {
	setup() {
		...
	},
	directives: {
		highlight: {
			...
		}
	}
}
```
3) Global app definition:
```
const app = createApp();

app.directvie('hightlight', {
	...
})
```

Directives can define new behaviour for the lifecycle of an element and take these optional arguments:
```
// called before bound element's attributes 
// or event listeners are applied 
created(el, binding, vnode) { 
	// see below for details on arguments 
}, 

// called right before the element is inserted into the DOM. 
beforeMount(el, binding, vnode) {}, 

// called when the bound element's parent component // and all its children are mounted. 
mounted(el, binding, vnode) {}, 

// called before the parent component is updated 
beforeUpdate(el, binding, vnode, prevVnode) {}, 

// called after the parent component and 
// all of its children have updated 
updated(el, binding, vnode, prevVnode) {}, 

// called before the parent component is unmounted
beforeUnmount(el, binding, vnode) {}, 

// called when the parent component is unmounted unmounted(el, binding, vnode) {}
```

Note that the name conventions suppose that the directive could be used like v-name (and not vName or name)


https://vuejs.org/guide/reusability/custom-directives
