# Site Red-Out
Red out your site for Net Neutrality.

> The HTML and CSS code included in this guide is mobile friendly, does not include trackers of any sort, is open source, and is licensed under the [MIT License](license.md). If you notice any mistakes, please feel free to make a PR and I will get it merged as quickly as possible.
>
> Thank you for defending Net Neutrality! -- Foxtrek_64, Owner of LuzFaltex

### Previews: [Raw](https://www.luzfaltex.com/redout.html) | [Live](https://www.luzfaltex.com)

## Getting started
1. Download [redout.html](redout.html)
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

WoltLab version with time-sensitivity
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

Place the following in the `header` template above the `#top` element
```html
{if TIME_NOW|date:'Y m j' >= '2017 12 12'}<iframe class="redout" src="https://www.luzfaltex.com/redout.html"></iframe>{/if}
```
