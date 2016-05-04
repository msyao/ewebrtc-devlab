###DevLab for AT&T Enhanced WebRTC
####Sample App and Exercise Apps
----
This version is self-contained with all files needed to start your Node Express app on your laptop/desktop.

#####Pre-requisites:
----
1. Node installed on your laptop/desktop.
  * If not, get Node.js from [nodejs.org](https://www.nodejs.org)
  * Make sure you install Node.js as Administrator on your machine
2. Obtain credentials from [AT&T Developer Portal](https://developer.att.com) to use [Enhanced WebRTC](http://developer.att.com/enhanced-webrtc)
  * Login to your account on AT&T Developer Portal
  * Enhanced WebRTC Org domain must have been configured in your account
  * You will need to create an App in DevPortal with `Account Id` scope
  * After creating the App, portal shows your App Key and App Secret
  * If you attended the Bootstrap session, you already know how to get these. If not, check the session's recordings.

> NOTE: [Premium-level access](http://developer.att.com/pricing) is needed to use Enhanced WebRTC.

#####Instructions:
----
1. Git clone this [repo](https://github.com/attdevsupport/ewebrtc-devlab).
  * Or get the [zip](https://github.com/attdevsupport/ewebrtc-devlab/archive/master.zip). Extract it to a local folder.
2. Open a terminal/command window.
  * `cd` to that local folder
  * Open `app.js` in an editor
  * Replace `<your_app_key>`, `<your_app_secret>`, `<your_ewebrtc_domain>` with your values
  * Save and Close `app.js`
3. In the terminal:
  * Enter the command ```npm install``` 
  * This downloads and installs required npm modules
  * After install is done, Enter the command ```npm start```
  * This will start the Node/Express Web Server.
4. You should see logs like the following:
```
  ...
  ...
  ...
  api_env: 'sandbox',
  host: '127.0.0.1',
  port: 9001,
  cors_domains: [ '127.0.0.1:9001' ],
  app_config_url: 'https://127.0.0.1:9001/config',
  app_tokens_url: 'https://127.0.0.1:9001/tokens',
  app_e911ids_url: 'https://127.0.0.1:9001/e911ids' }
HTTPS server listening on host:  127.0.0.1  at port  9001
```
> NOTE: App Key, App Secret etc. configuration now goes inside app.js. This is different from previous versions which used package.json for configuration.

#####Sample App:
----
1. Open Chrome browser. Go to the App's [Accound Id Demo page](https://127.0.0.1:9001) at https://127.0.0.1:9001

> Why is HTTPS needed?
> * Media capture in Browsers (getUserMedia API) requires the Web Page to come from secure HTTPS host


#####Chrome SSL Alert:
----
* This demo is set up with self-generated certificate. Chrome alerts the user to such situations.
* The first time you visit the demo page, Chrome alerts you with `Your connection is not private` message
  * Error: `NET::ERR_CERT_AUTHORITY_INVALID`

![alt text][cwsc-png]
[cwsc-png]: https://github.com/attdevsupport/ewebrtc-devlab/raw/master/public/img/chrome-warning-self-cert.png "Chrome Warning for Self-generated Certificate"

* To ignore the warning and proceed to the demo page:
  * Click `Advanced` and then 
  * Click `Proceed to 127.0.0.1 (unsafe)`

![alt text][cpsc-png]
[cpsc-png]: https://github.com/attdevsupport/ewebrtc-devlab/raw/master/public/img/chrome-proceed-with-self-cert.png "Proceed to Web Page"

#####Important:
----
* sample.cert and sample.key are provided only for quick-start conveniece.
* Use these only your local machine, and only for quick-start learning on your laptop/desktop.

> DON'T use the sample.cert, sample.key anywhere else. Replace with your own secure certiciate and key. Consult your Web or Security Admin for more information.

#####Node/NPM Errors:
----
* If you see errors like `Error: Cannot find module 'express'`, npm install did not happen successfully.
  * Make sure `npm install` finished with out errors.
* Stick with `127.0.0.1`. Other names like local, localhost, mymachinename etc. may not work.
* If npm is stuttering, make sure you are connected to open, proxy-less Internet

#####WebRTC App Media Issues:
----
* Make sure you are connected to Internet without VPN or other firewall restrictions.

#####Further Information:
----
* [AT&T Developer Portal](https://developer.att.com)
* [Enhanced WebRTC](https://developer.att.com/enhanced-webrtc)
* [Getting Started](http://developer.att.com/enhanced-webrtc/sdk)
* [Docs](http://developer.att.com/enhanced-webrtc/docs)
* [FAQs on Enhanced WebRTC](http://developer.att.com/enhanced-webrtc/support/faqs/enhanced-webrtc-api-faqs)
* [AT&T API FAQs](http://developer.att.com/enhanced-webrtc/support/faqs)
* [Support](http://developer.att.com/support)
* [Pricing](https://developer.att.com/pricing)

