
add "electron-builder.json" file into the root that goes:
```
{
	"appId": "com.i-nitials.name-of-the-app",
	"files": ["dist-electron", "dist-react"],
	"icon": "path-to-icon",

	"mac": {
	"target": "dmg"
	},

	"linux": {
		"target": "AppImage",
		"category": "Utility"
	},

	"win": {
		"target": ["portable", "msi"]
	}
}
```

then add new scripts to the package.json:

```
"dist:mac": "npm run transpile:electron && npm run build && electron-builder --mac --arm64",
"dist:linux": "npm run transpile:electron && npm run build && electron-builder --linux --x64",
"dist:win": "npm run transpile:electron && npm run build && electron-builder --win --x64"
```

After this you should be able to run "npm run dist:mac" and get a dmg file that can be distributed. If you target any other architecrue, you could also do a different script for that