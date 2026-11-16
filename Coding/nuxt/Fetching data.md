
Data is fetched using useFetch hook:

```
const { data: products } = useFetch('link")
```

Name after data: in deconstructor is the name of the variable we gonna use:

```
<div v-for="product in products">

...

</div>
```