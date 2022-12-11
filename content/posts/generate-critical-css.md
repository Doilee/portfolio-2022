+++
author = "Matthijs Dam"
title = "Penthouse: automatically generate above-the-fold critical CSS"
date = "2022-12-11"
description = "Guide to generating critical CSS in your webapp using penthouse"
tags = [
    "seo",
]
+++

Parsing and generating critical CSS can be a useful technique for improving the performance of your website. Critical CSS refers to the portion of your stylesheets that are necessary for rendering the above-the-fold content of your webpage. By extracting this critical CSS and inlining it into the head of your HTML document, you can ensure that your page is rendered quickly and efficiently.

Here's a simple example of how to parse and generate critical CSS using [penthouse](https://www.npmjs.com/package/penthouse):

First, you'll need to install the package from npm:

```bash
npm install penthouse
```

Next, you can use the penthouse module to extract the critical CSS for a given URL like this:

```js
const penthouse = require('penthouse');

// Load the URL of the page you want to extract critical CSS from
const url = 'https://www.example.com';

// Extract the critical CSS
penthouse({
    url,
    width: 1300,
    height: 900
}, (err, criticalCss) => {
// Output the critical CSS to the console
    console.log(criticalCss);
});
```

The penthouse function takes two arguments: an options object and a callback function. The options object allows you to specify the URL of the page to extract critical CSS from, as well as the width and height of the viewport. The callback function will be called once the critical CSS has been extracted, and it will be passed two arguments: an error object (which will be null if there are no errors), and the extracted critical CSS.

Once you have the critical CSS, you can inline it into the head of your HTML document like this:

```HTML
<!DOCTYPE html>
<html>
  <head>
    <style>
      /* Paste the critical CSS here */
    </style>
  </head>
  <body>
    ...
  </body>
</html>
```
Inlining the critical CSS like this ensures that it will be applied to the above-the-fold content of your page as soon as it is loaded, allowing your page to render quickly and efficiently.

Keep in mind that this is just a simple example of how to parse and generate critical CSS using Javascript. There are many other options and configurations that you can use to customize the process to suit your needs. For more information, be sure to check out the [penthouse](https://www.npmjs.com/package/penthouse) package on npm.