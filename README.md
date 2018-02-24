# simple-emojione-picker.js

An extremely simple emoji picker written in native JS. This has very minimal features, it does not provide any way to output the emoji, it just provides a UI for users to select emoji. For a more fully featured picker please check out this, my project was somewhat based off of it: https://github.com/mervick/emojionearea

[Live Demo](https://kufii.github.io/simple-emojione-picker.js/)

## Usage

The picker is dependent on emojione.js. You can find it here: https://github.com/emojione/emojione/blob/master/lib/js/emojione.js

You must also link emojionepicker.css and emojionepicker.js

Create the picker by calling `EmojiPicker(context, config)`

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Emoji Picker Tester</title>

	<link rel="stylesheet" href="emojionepicker.css" />

	<script src="https://cdn.rawgit.com/emojione/emojione/9a81e8462ea5c1efc8e4f2947944d0a248b8ec73/lib/js/emojione.min.js"></script>
	<script src="emojionepicker.js"></script>
</head>
<body>
	<script>
		let picker = EmojiPicker(document.body, {
			width: '285px',
			height: '300px'
		});
	</script>
</body>
</html>
```

## Options

Configuration parameters can be passed by adding a cfg object parameter. Eg.

```javascript
let picker = EmojiPicker(document.querySelector('#picker'), cfg);
```

**`onselect`**

Captures the selected emoji.

**type:** `function(unicode, shortname)`

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'), {
	onselect(unicode, shortname) {
	}
});
```

**`onPageChange`**

Captres page change event

**type:** `function(index)`

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'), {
	onPageChange(pageIndex) {
	}
});
```

**`onToneChange`**

Captures skin tone change event

**type:** `function(index)`

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'), {
	onToneChange(toneIndex) {
	}
});
```

**`search`**

Show search box

**type:** `boolean`  
**default:** `true`

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'), {
	search: false
});
```

**`tones`**

Show tone buttons

**type:** `boolean`  
**default:** `true`

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'), {
	tones: false
});
```

**`width`** and **`height`**

Sets the width/height of the picker

**type:** `string`  
**default:** `auto`

Example:

```javascript
let picker = EmojiPicker(document.body, {
	width: '285px',
	height: '300px'
});
```

## Functions

**`selectPage(index)`**

Programatically change the picker's page

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'));
picker.selectPage(3);
```

**`selectTone(index)`**

Programatically set the selected tone

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'));
picker.selectTone(3);
```

**`search(query)`**

Programatically perform a search

Example:

```javascript
let picker = EmojiPicker(document.querySelector('#picker'));
picker.search('heart');
```
