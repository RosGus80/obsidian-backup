
Need this meta tag in the doc:
`<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

And then able to use classes conditional on media queries:
`<img class="w-16 md:w-32 lg:w-48" src="..." />`

| Key   | Size             | CSS                               |
| ----- | ---------------- | --------------------------------- |
| `sm`  | 40rem _(640px)_  | `@media (width >= 40rem) { ... }` |
| `md`  | 48rem _(768px)_  | `@media (width >= 48rem) { ... }` |
| `lg`  | 64rem _(1024px)_ | `@media (width >= 64rem) { ... }` |
| `xl`  | 80rem _(1280px)_ | `@media (width >= 80rem) { ... }` |
| `2xl` | 96rem _(1536px)_ | `@media (width >= 96rem) { ... }` |
If you use max- prefix for media query class (max-xl), corresponding css would flip the >= sign and make it the < sign