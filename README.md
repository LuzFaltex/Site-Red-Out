# Site-Red-Out
Red out your site for Net Neutrality

## Getting started
1. Download [/redout.html](redout.html)
2. Open `redout.html` in a text editor and change `LuzFaltex.com` to the domain of your site. Save your changes
3. Upload `redout.html` to your root site directory

> If your site is located at `www.example.com`, your `redout.html` should be located at `www.example.com/redout.html`

4. Insert the following code into the header of your site:

```html
<style>
    .redout {
        width: 100%;
        height: 100%;
    }
</style>
<iframe class="redout" src="https://www.luzfaltex.com/redout.html"></iframe>
```

PHP version with time-sensitivity:
```php
<?php if (new DateTime() > new DateTime("2017-12-12")) { ?>
<iframe class="redout" src="https://www.luzfaltex.com/redout.html"></iframe>
<?php } ?>
```

Optionally, you can place the css into your site's css document.

---

>Pro tip! If you're using WoltLab, use the following instead:

```css
.redout {
	width: 100%;
	height: 100%;
	display: none;
}
body[data-page-id="1000"] .redout{
	display: flex;
}
```
Replace `1000` with the ID of your page (pull open your F12 editor to find it easily)

```html
{if TIME_NOW|date:'Y m j' >= '2017 12 12'}<iframe class="redout" src="https://www.luzfaltex.com/redout.html"></iframe>{/if}
```
The `{if}{/if}` piece ensures that it only displays on or after the 12th of December