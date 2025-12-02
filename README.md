# firefox-android-back-button-close-tab
Tampermonkey/violentmonkey script enabling back button to close tab on Firefox on Android.


## Usage:
Create a new script and copy the following to the user script section.
```
// This runs on every page
if (window.history.length <= 1) {
    // We are at the start of the tab history
    // Listen for a back button press (this is hard to trap in JS on mobile, but possible via 'popstate')
    window.addEventListener('popstate', function(event) {
         window.close(); // Try to force close the tab
    });
}
```

Then save and it should just start working with the intended behavior, i.e. to close the tab if there is no more history to scroll back. And then get back to last sctive tab.

The script has been tested on Motorola Edge 50 pro with Android 16 and Firefox 145.0.2 using violentmonkey 2.31.0.
