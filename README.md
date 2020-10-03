# websiteCloner
Html, javascript and css

How to clone a website (download HTML,CSS, JavaScript, Fonts and Images) using Website Scraper in Node.js

1. Install Website Scrapper Puppeteer

npm install website-scraper website-scraper-puppeteer

2. Create download script
 // index.js
const scrape = require('website-scraper');
const PuppeteerPlugin = require('website-scraper-puppeteer');
const path = require('path');

scrape({
    // Provide the URL(s) of the website(s) that you want to clone
    // In this example, you can clone the Our Code World website
    urls: ['https://ourcodeworld.com/'],
    // Specify the path where the content should be saved
    // In this case, in the current directory inside the ourcodeworld dir
    directory: path.resolve(__dirname, 'ourcodeworld'),
    // Load the Puppeteer plugin
    plugins: [ 
        new PuppeteerPlugin({
            launchOptions: { 
                // If you set  this to true, the headless browser will show up on screen
                headless: true
            }, /* optional */
            scrollToBottom: {
                timeout: 10000, 
                viewportN: 10 
            } /* optional */
        })
    ]
});

3. Run script
node index.js

Happy coding!
