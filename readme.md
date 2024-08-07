## A json-formatted and machine-parsable map of emoji codes to data

extracted from the unicode page https://www.unicode.org/emoji/charts/full-emoji-list.html
via
```js
const emoji_map = { };
let code = null;
$x("//tr/td[@class!='rchars']").forEach(x => {
	switch (x.className) {
	case "code":
		code = x.innerText;
		emoji_map[code] = { };
		break;
	default:
		emoji_map[code][x.className] = x.innerText;
	}
});
```
