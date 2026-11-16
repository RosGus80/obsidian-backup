1)
```
npm i tailwindcss @tailwindcss/postcss;
```
2)
postcss.config.js:
```
export default {  plugins: ["@tailwindcss/postcss"],};
```
3)
```
@import "tailwindcss";
```


Or (better approach for my liking):

1)
```
npm install -D tailwindcss @tailwindcss/vite
```
2) vite.config.:
```
import { defineConfig } from "vite";
import tailwindcss from "@tailwindcss/vite";
export default defineConfig({  
	plugins: [    
		tailwindcss(),  
	],
});
```
3) style.css:
```
@import "tailwindcss";
```

Then just use tailwind classes


# NUXT

Install same modules (tailwindcss, @tailwind/vite), but add them to your nuxt config:

```
import tailwindcss from "@tailwindcss/vite";export default defineNuxtConfig({  
	compatibilityDate: "2025-07-15",  
	devtools: { enabled: true },  
	vite: {   
		plugins: [      
			tailwindcss(),    
		],  
	},
});
```

Then create a global css file and add it to config as well:
```
export default defineNuxtConfig({  
	compatibilityDate: "2025-07-15",  
	devtools: { enabled: true },  
	css: ['assets/css/main.css'],
```