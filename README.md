# simple-emojione-picker.js

An extremely simple emoji picker written in native JS. This has very minimal features, it does not provide any way to output the emoji, it just provides a UI for users to select emoji. For a more fully featured picker please check out this, my project was somewhat based off of it: https://github.com/mervick/emojionearea

## Usage

The picker is dependent on emojione.js. You can find it here: https://github.com/emojione/emojione/blob/master/lib/js/emojione.js

````
<div id='picker'></div>
<script>
	let picker = EmojiPicker(document.querySelector('#picker'));
</script>
````

## Options

Configuration parameters can be passed by adding a cfg object parameter. Eg.

````
let picker = EmojiPicker(document.querySelector('#picker'), cfg);
````

**`onselect`**

Captures the selected emoji.

**type:** `function(unicode, shortname)`

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'), {
	onselect: (unicode, shortname) => {
	}
});
````

**`onPageChange`**

Captres page change event

**type:** `function(index)`

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'), {
	onPageChange: pageIndex => {
	}
});
````

**`onToneChange`**

Captures skin tone change event

**type:** `function(index)`

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'), {
	onToneChange: toneIndex => {
	}
});
````

**`search`**

Show search box

**type:** `boolean`  
**default:** `true`

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'), {
	search: false
});
````

**`tones`**

Show tone buttons

**type:** `boolean`  
**default:** `true`

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'), {
	tones: false
});
````

## Functions

**`selectPage(index)`**

Programatically change the picker's page

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'));
picker.selectPage(3);
````

**`selectTone(index)`**

Programatically set the selected tone

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'));
picker.selectTone(3);
````

**`search(query)`**

Programatically perform a search

Example:

````
let picker = EmojiPicker(document.querySelector('#picker'));
picker.search('heart');
````
