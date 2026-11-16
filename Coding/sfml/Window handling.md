
### Events handling 

```
const auto onClose = [&window](const sf::Event::Closed&) {
	window.close();
};

const auto onKeyPressed = [&window](const sf::Event::KeyPressed& keyPressed) {
	if (keyPressed.scancode == sf::Keyboard::Scancode::Escape) 
		window.close();
};

while (window.isOpen()) {
	window.handleEvents(onClose, onKeyPressed);
}
```

(may be done manually):

```
while (window.isOpen()) {
	// onClose
	if (event->is<sf::Event::Closed>()) {
		window.close();
	}

	// onKeyPressed
	if (const auto* keyPressed = event->getIf<sf::Event::KeyPressed>()) {
		if (keyPressed.scancode == sf::Keyboard::Escape) {
			window.close();
		}
}
```