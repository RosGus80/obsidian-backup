### 'result' var is used as a container for procedure return values

```
proc resultThing(): string =
	for letter in @['a', 'b', 'c']:
		result.add(letter)

echo resultThing()
```

### Types are created using 'type' keyword:

```
type 
	Animal = object
		species: string
		age: int
		skills: seq[string]
```

Also may reference other object on type field:

![[Зачем ref obj]]

The immutable types (created using 'let' keyword) may still change its conatinings if the pointers remain the same:

![[Как можно мутировать иммутабельные типы]]

### Using ordinals:

![[Ordinals]]
