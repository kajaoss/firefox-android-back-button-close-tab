# firefox-android-back-button-close-tab
Violentmonkey script enabling back button to close tab on Firefox on Android. The script should work also with Tampermonkey but I haven't tested it.


## Usage:
Create a new script and copy the following to the user script section.
```
// This runs on every page
if (window.history.length <= 1) {
    // We are at the start of the tab history
    // Listen for a back button press via 'popstate'
    window.addEventListener('popstate', function(event) {
         window.close(); // Try to force close the tab
    });
}
```

Then save and it should just start working with the intended behavior, i.e. to close the tab if there is no more history to scroll back. And then it gets back to the previous active tab.

The script has been tested on Motorola Edge 50 pro with Android 16 and Firefox 145.0.2 using violentmonkey 2.31.0. If there is any problems please open issue with details of phone model, os version, and firefox version.
