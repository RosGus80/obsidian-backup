
In the app dir, the routing is as:

index.jsx matches the / route
(name).jsx matches the /(name) route

+not-found.jsx mathces the 404 error route

In the app dir, (tabs) dir is used to display routes in the bottom bar. _layout.jsx must also be created in the (tabs) dir

To add tabs field:
```
<Tabs>
<Tabs.Screen name="index"
	options={{
		title: 'Home',
		tabBarIcon: ({ color, focused }) => (
			<Ionicons name={focused ? 'home-sharp' : 'home-outline'} color={color} size={24} />),
}}
/>

<Tabs.Screen name="about"
	options={{
		title: 'About',
		tabBarIcon: ({ color, focused }) => (
			<Ionicons name={focused ? 'information-circle' : 'information-circle-outline'} color={color} size={24}/>),
}}
/>
</Tabs>
```
