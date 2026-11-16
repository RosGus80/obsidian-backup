
```
<div class="bg-white text-black dark:bg-blue-400 dark:text-green-50">

<h1>Text</h1>

</div>
```

dark: query works if the dark mode is enabled. Supported natively


### Project-wide preference-based light/dark themes

If you do :root {
	...
}

And define color variables, you'll have two themes based on system preference. Then you'll need to map these values for tailwind to know the colors and be able to use it as tailwind classes:

@theme {
	--color-bg: var(--color-bg);
	--color-bg-dark: var(--color-bg-dark);
	--color-bg-light: var(--color-bg-light);
	--color-text: var(--color-text);
	...
}

Then you can use it globally and colors will react to system preference change., and you wont need to use dark: utility as respective colors will change values according to user preference