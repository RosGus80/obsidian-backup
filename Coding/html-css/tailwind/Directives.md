
In main css file can config different directives:

@theme:
Directive for project design vars and stuff. Also notice breakpoint-3xl: it's a custom media query size to be used like `3xl:flex`, like predefined breakpoints

```
@theme {  
	--font-display: "Satoshi", "sans-serif";  
	--breakpoint-3xl: 120rem;  
	--color-avocado-100: oklch(0.99 0 0);  
	--color-avocado-200: oklch(0.98 0.04 113.22);  
	--color-avocado-300: oklch(0.94 0.11 115.03);  
	--color-avocado-400: oklch(0.92 0.19 114.08);  
	--color-avocado-500: oklch(0.84 0.18 117.33);  
	--color-avocado-600: oklch(0.53 0.12 118.34);  
	--ease-fluid: cubic-bezier(0.3, 0, 0, 1);  
	--ease-snappy: cubic-bezier(0.2, 0, 0, 1);  /* ... */}
```

@utility: 
To define your custom utility classes:
```
@utility tab-4 {  tab-size: 4;}
```

@apply:
use the utility class inside css:
```
.select2-dropdown {  @apply rounded-b-lg shadow-md;}
```

@layer:
used to define default classes for different layers of elements.
Body - for tags, component - for classes:
```
@layer base {
	body {
		@apply bg-indigo-950 text-rose-600;
	}
}
```

```
@layer components {  
	.card {    
		background-color: var(--color-white);   
		border-radius: var(--radius-lg);    
		padding: --spacing(6);    
		box-shadow: var(--shadow-xl);  
	}
}
```

