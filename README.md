# puppeteer-sample

Puppeteer is the Google Chrome Headless by Google Chrometeam.

## Why should i use Puppeteer ?

- automation made easy
- testing easy
- screenshot easy
- building easy


>Puppeteer is a Node library which provides a high-level API to control headless Chrome or Chromium over the DevTools Protocol. It can also be configured to use full (non-headless) Chrome or Chromium.

## Installation 

Let's install Puppeteer
```
$ npm i --save puppeteer 
```

## Examples 

Yout can run this with:

```
$ npm index.js
```

run desktop default size 800x600, `index.js`

```js=
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://google.com');
  await page.screenshot({path: './screen/screenshot.png'});

  await browser.close();
})();
```

output to print pdf, `index.js`

```js=
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();  
  await page.goto('https://google.com', {waitUntil: 'networkidle2'});
  await page.pdf({path: './pdf/screen.pdf', format: 'A4'});

  await browser.close();
})();

```
Don't miss your folder, upto you.
## Configuration

The available options are [documented here](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#)

#### For example

How to check after all event trigger?

```js
await page.goto('https://google.com', {waitUntil: 'networkidle2'});
```

> When to consider navigation succeeded, defaults to load. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
 

```js
waitUntil: 'networkidle2'
```

`load` - consider navigation to be finished when the load event is fired.

`domcontentloaded` - consider navigation to be finished when the DOMContentLoaded event is fired.

`networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least 500 ms.

`networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least 500 ms.
 

#### You can find more [puppeteer's API](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#)


## References

[stackoverflow](https://stackoverflow.com/questions/tagged/puppeteer)
[puppeteersandbox](https://puppeteersandbox.com/)
[puppeteer-examples](https://github.com/checkly/puppeteer-examples)
