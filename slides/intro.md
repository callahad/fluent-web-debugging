# Debugging the Mobile Web

***

Wowowowowowowowow.

---

# Quick Introductions

***

# Dan Callahan

* Developer / Advocate, Mozilla
* Works from Minneapolis, MN.
* @callahad
* [http://dancallahan.info](http://dancallahan.info)

***

# Mike Taylor

* Web Compatibility Engineer, Mozilla
* Works from Austin, TX.
* [http://crappytld.club](https://miketaylr.com)
* [https://webcompat.com](https://webcompat.com)

---

# Outline:

0. Getting set up
1. Debugging JavaScript Stuff
2. Debugging CSS Stuff
3. Break!
4. Debugging Performance Stuff
5. Debugging Network Stuff
6. Freestyle debugging session (time willing)

---

# Let's get set up for Remote Debugging.

***

## Step 0. Connect your phone to your computer over USB.

***

# Android

The following steps and images courtesy [developer.chrome.com](https://developer.chrome.com/devtools/docs/remote-debugging)

(Content available under the CC-By 3.0 license)

***

### 1. Enable USB debugging
On your Android device, select Settings > Developer options.
<img src="slides/images/settings-dev-options-on.png">

***

### (Maybe) 2. Tap Tap Tap Tap Tap Tap Tap
<img src="slides/images/about-phone-build-num.png">

***

### In Developer options, select the USB debugging checkbox:
<img src="slides/images/usb-debugging-on.png">

***

# iOS

***

### 1. Enable the Web Inspector setting from Settings > Safari > Advanced
<img src="slides/images/mobile-safari-settings.png">

***

### (Maybe) 2. Enable the Developer Menu in Safari
<img src="slides/images/desktop-safari-prefs.png">

---

# Now let's connect to our devices.

***

# Firefox
# ([Dev Edition™](https://www.mozilla.org/en-US/firefox/developer/))

Using at least v36 or up

(lower versions require manually adb wrangling)

((ok, great))

***

### 1. Enable remote debugging on ur phone

***

### Menu > Settings

<img data-src="slides/images/firefox-mobile-settings.png">

***

### Enable Remote Debugging

<img class="stretch" data-src="slides/images/firefox-mobile-enablerd.png">

***

# Bust open WebIDE

***

### Tools > Web Developer > WebIDE

<img data-src="slides/images/webide-runtime.png">

***

### Accept the incoming connection

<img data-src="slides/images/firefox-incoming-connection.png">

***

### Select a tab to connect to

<img data-src="slides/images/webide-openapp.png">

***

# BAM

<img data-src="slides/images/webide-connected.png">

***

# Chrome

Using at least v32 or up and with Android 4.0+.

***

### 1. Open chrome://inspect

Make sure "Discover USB Devices" is checked.

<img data-src="slides/images/chrome-inspect.png">

***

# BAM

<img data-src="slides/images/chrome-connected.png">

***

# Safari

Using Safari 6 and up and at least iOS 6.

***

### 1. Make sure Safari Mobile is running

***

### Select Develop > Device Name > Tab

<img data-src="slides/images/safari-develop.png">

***

### BAM

<img data-src="slides/images/safari-connected.png">
