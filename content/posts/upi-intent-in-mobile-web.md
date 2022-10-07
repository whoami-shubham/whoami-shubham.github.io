---
layout: post
title: Android intents for UPI Apps from Chrome
summary: "Open UPI apps from browser using deeplink"
date:   2022-10-07
tags: [Web,UPI,Payment]
---

 
I was looking for ways to open sepcific UPI apps from chrome using deeplink for payment, because if you click on a deeplink in mobile browser, it will open a bottomsheet 
showing all available apps that can understand the deeplink.

![image](https://user-images.githubusercontent.com/28999685/194614304-0269e129-9543-462b-8532-142ec3f66b5a.png)

then I found this [documentation](https://developer.chrome.com/docs/multidevice/android/intents) 
It had most of details to create a intent from browser, however I couldn't found more details about scheme there.
after trying different schemes values following format worked for me.

```js
const url  = `intent://${paymentLink}#Intent;scheme=upi://pay;package=${appPackageName};end`


```
here is some sample code for reference.

<iframe src="https://codesandbox.io/embed/chrome-upi-intents-uwjpkg?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="chrome upi intents"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

