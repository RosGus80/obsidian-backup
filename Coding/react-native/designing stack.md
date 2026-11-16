
```
<Stack.screen options={
	title: '',
	см. в доках
} />
```

https://docs.expo.dev/router/advanced/stack/
https://reactnavigation.org/docs/headers/#sharing-common-options-across-screens

Хороший параметр: presentation. Отвечает за способ перехода на новую страницу. Например, presentation: 'modal' будет открывать временные окна, которые легко смахнуть

Для определения поведения стеков (и табов) для отдельных страниц, в файле _layout.tsx можно поступить следующим образом:

```
<Stack screenOptions={{
	headerShown: false,
}}> 

	<Stack.Screen name="index" />
	<Stack.Screen name="login" 
		options = {{
			// опции экрана (то же, что screenOptions, только для конкретного экрана)
			headerShown: true,
			presentation: "modal",
		}}

</Stack>
```

Причем чтобы Stack.Screen понимал, к какой странице он относится, name должен быть заполнен согласно названию файла страницы. То есть если у нас есть index.tsx и login.tsx, то у нас должны быть name="index" и name="login" соответственно