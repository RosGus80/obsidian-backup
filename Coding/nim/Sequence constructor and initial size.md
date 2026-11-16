
We can allocate some pre defined amount of space for sequence if we know it'll contain at least this amount of elements:

```
var s: seq[int] = newSeq[int](8)
```

In this case, 8. This makes addition of first 8 elements slightly faster because we dont need to allocate new memory and copy our sequence for this purpose