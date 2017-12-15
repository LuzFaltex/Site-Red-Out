# Site Red-Out
Red out your site for Net Neutrality.

> The HTML and CSS code included in this guide is mobile friendly, does not include trackers of any sort, is open source, and is licensed under the [MIT License](license.md). If you notice any mistakes, please feel free to make a PR and I will get it merged as quickly as possible. Oh, and quick note: I am not affiliated with [Reddit](https://www.reddit.com) or their [similar-looking protest](https://www.reddit.com/r/FFTFCSSTEST/). This is my code from the ground up, though their CSS was helpful for reference.
>
> Thank you for defending Net Neutrality! -- Foxtrek_64, Owner of LuzFaltex

### Previews: [Raw](https://www.luzfaltex.com/blackout.html) | [Live](https://www.luzfaltex.com)

## Getting started
1. Download [blackout.html](blackout.html)
2. Open `blackout.html` in a text editor and change `LuzFaltex.com` to the domain of your site. Save your changes
3. Upload `blackout.html` to your root site directory

> If your site is located at `www.example.com`, your `blackout.html` should be located at `www.example.com/blackout.html`

4. Insert the following code into the header of your site:

```html
<style>
    .redout {
        width: 100%;
        height: 100%;
    }
</style>
<iframe class="redout" src="https://www.luzfaltex.com/blackout.html"></iframe>
```

PHP version with time-sensitivity:
```php
<?php if (new DateTime() > new DateTime("2017-12-12")) { ?>
<iframe class="redout" src="https://www.luzfaltex.com/blackout.html"></iframe>
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
{if TIME_NOW|date:'Y m j' >= '2017 12 12'}<iframe class="redout" src="https://www.luzfaltex.com/blackout.html"></iframe>{/if}
```
