
To setup a react project for being built via electron, first, we should create a react project:
`npm create vite .`
choose react + TS (or JS if you are lightheaded) and configure your react project as normal.

Install electron using
`npm install --save-dev electron`
Then, in the src folder, create 'electron' folder and add a main.ts file there.
```
import { app, BrowserWindow } from "electron";

import path from "path";


app.on('ready', () => {

const mainWindow = new BrowserWindow({
});

  
mainWindow.loadFile(path.join(app.getAppPath(), 'dist-react', 'index.html'));

});
```

in vite.config.js configure it so that the react build would be separate from the electron build:
```
export default defineConfig({
	plugins: [react()],
	base: './',
	build: {
	outDir: 'dist-react',
	}
});

```

add the "main" property into the package.json:
```
...
"main": "dist-electron/main.js",
...
```

In order for it to call an existing file, we should have the "dist-electron" build folder so we redefine the tsconfig.app.jelecson, adding
`"exclude": ["src/electron"]`
and adding the tsconfig.json file into the src/electron:
```
{
	"compilerOptions": {
		"strict": true,
		"target": "ESNext",
		"module": "NodeNext",
		"outDir": "../../dist-electron",
		"skipLibCheck": true
	}

}
```

Adding into package.json:
```
"scripts": {
...
	"transpile:electron": "tsc --project src/electron/tsconfig.json"
...
}
```
for building the ts electron project into the js build folder

Optional, but convenient, move the react files that were created, into the src/ui folder

Add scripts to the package.json as well:
```
"scripts": {
	"dev:react": "vite",
	"dev:electron": "electron .",
	"build": "tsc -b && vite build",
	"lint": "eslint .",
	"preview": "vite preview"
},
```

At this point you should be able to run
`npm run build` 
and then
`npm run dev:electron` 
and see the window of the app


[[builder setup|-> Set up the dist builder]]
