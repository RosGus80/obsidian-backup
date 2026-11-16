
Any enum type of info may be numbered as ordinal type. Example:

```
type Directions = enum
top = "Y, not-X", left = "-X, not-Y", bottom = "-Y, not-X", right = "X, not-Y"

for dir in Directions:
	echo ord(dir)
```

Output:

```
0
1
2
3
```

Because enums are ordinals, they have the `low`, `high`, `inc`, `dec`, and `ord` methods defined, where

- `low` gives the lowest possible value
- `high` give the highest possible value
- `inc` increments
- `dec` decrements
- `ord` gives the integer value of the enum
- `Directions` is a cast that gives an enum from an integer
