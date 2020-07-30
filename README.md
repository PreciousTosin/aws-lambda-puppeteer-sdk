# aws-lambda-puppeteer-sdk

This is for setting up dependency layer for puppeteer and headless chrome in AWS Lambda using chrome-aws-lambda and puppeteer-core.

This version is for puppeteer-core v5.1.0 and puppeteer v5.1.0

**STEPS TO USE CODE LOCALLY**

- First clone the repository using `git clone command`
- `cd` into `nodejs` folder
- Run `npm install` in the nodejs. This will install puppeteer which is necessary for local testing
- Wait for dependencies to install, they may take some time depending on your internet speed.

These next steps fixes an issue with path error causes by changes in file path in this puppeteer verion

- Go to `nodejs/node_modules/chrome-aws-lambda/source/puppeteer/lib`
- Replace `Line 6` of the 3 files: `Browser.js, FrameManager.js, Page.js` with `Super = require('puppeteer-core/lib/cjs/common/Browser').BrowserContext`

**STEPS TO USE CODE IN CREATING LAMBDA LAYER**

- If you don't have a local copy used for testing go to next step else `cd` into `nodejs` folder and delete `node_modules` folder with `rm -rf node_modules`
- if you don't have an existing local repo, clone the repository using `git clone command`
- `cd` into `nodejs` folder
- Run `npm install --production` in the nodejs.
- Wait for dependencies to install, they may take some time depending on your internet speed.

These next steps fixes an issue with path error causes by changes in file path in this puppeteer verion

- Go to `nodejs/node_modules/chrome-aws-lambda/source/puppeteer/lib`
- Replace `Line 6` of the 3 files: `Browser.js, FrameManager.js, Page.js` with `Super = require('puppeteer-core/lib/cjs/common/Browser').BrowserContext`
- Zip `nodejs` folder and upload to aws lambda
