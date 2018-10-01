![alt text](https://github.com/VergillR/rise-notifier-browser-extension-firefox/blob/master/icons/riseicon_128.png "RISE logo extension")
# RISE notifications for Mozilla Firefox

This is a browser extension for receiving RISE notifications for Mozilla Firefox and Firefox-based browsers (e.g. TOR browser, Waterfox, Pale Moon).
It checks up to 5 RISE addresses simultaneously; You do not have to be the owner of the given addresses, so you can give any address you like. The extension currently supports 7 languages (English, German, French, Spanish, Portuguese, Dutch and Russian).

Usage is straightforward: simply give 1 to 5 RISE addresses you want to follow. Notifications about transactions from or to the RISE address will be displayed within 60 seconds.

### Summary
* Receive notifications for up to 5 RISE addresses in 7 different languages
* Near real-time notifications (<60 seconds) for incoming and outgoing transactions for each given RISE address
* Shows basic public information for each address, such as the current amount of RISE and the name of the delegate (if the account holder of the address has voted)
* Shows current prices (RISE/USD and RISE/BTC)
* On startup, shows notifications for any missed transactions when the browser was not running

### Installation
Normally, you can find and install extensions from [Mozilla](https://addons.mozilla.org/).

Alternatively, you can download the unpackaged extension by cloning this repo:

`git clone https://github.com/VergillR/rise-notifier-browser-extension-firefox`

The unpackaged extension only runs temporarily (you need to add it every time the browser starts up) but it works. To manually add the extension:
1. open Firefox
2. enter "about:debugging" in the URL bar
3. click "Load Temporary Add-on"
4. open the extension's directory and select any file (e.g. *manifest.json*) inside the directory and click "Open"

### Adding extra languages
To add an extra language:
1. make a new folder inside the directory */_locales*
2. rename the new folder to the correct [locale](https://developer.chrome.com/webstore/i18n#localeTable) for the language. For example, for Korean, the folder should be called *ko*
3. copy the file */_locales/en/messages.json* and paste it inside the new directory
4. translate and replace all values of _"message"_ with the translations; so, translating the English word _address_ is replacing the word _"address"_ behind the _"message"_ with the translation. For example, translating it into Korean looks like:

    ```json
    "address": {
        "message": "주소"
    }
  
5. the _"locale"_ and _"momentformat"_ are used by [Moment.js](http://momentjs.com/); the locale is usually the same as the locale from step 2. For Korean, it would look like:

    ```json
    "locale": {
        "message": "ko"
    },
    "momentformat": {
      "message": "D MMMM YYYY, HH:mm:ss"
    }


### Data source
The extension gets its information from a server that uses the RISE API to communicate with the RISE network. Click [here](https://github.com/VergillR/rise-data-api) to check the code or to set up your own data source that the extension can use. You can choose your data source in the extension's *Options* screen.


### Privacy
Privacy is important. This extension uses the local storage on the device it is installed on, solely for the purposes for displaying necessary, public information. It never collects or asks for personal data (e.g. secret passphrase, login information or clipboard data). Stored data is not tracked, recorded, collected, shared or sold to third parties. Only use trusted data sources to ensure your privacy. At any time, you can delete all data stored on the device in the extension's *Options*. The code is open source (MIT license) so it can be fully reviewed.


### Notes
This extension only works for Mozilla Firefox and Firefox-based browsers.

For Google Chrome, Opera, Vivaldi, Brave and all other Chromium-based browsers: [click here](https://github.com/VergillR/rise-notifier-browser-extension)

For Microsoft Edge: [click here](https://github.com/VergillR/rise-notifier-browser-extension-edge)
