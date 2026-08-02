---
title: Redirect
layout: default_sinatra
---
# Download
Scan this QR Code with your phone to be redirected to the app store.

<img src="/assets/img/qr-code-redirect.svg" style="width: 300px; display: block; margin: 0 auto;">

Alternatively, click the buttons below to visit the app store for your phone:

<div id="app-icons">
    <a href="https://play.google.com/store/apps/details?id=cl.emilym.sinatra"><img src="/assets/img/googleplay.png"/></a>
    <a href="https://apps.apple.com/au/app/sinatra-for-canberra/id6739419456"><img src="/assets/img/appstore.svg"/></a>
</div>

<script>
    // https://stackoverflow.com/questions/21741841/detecting-ios-android-operating-system
    function getMobileOperatingSystem() {
        var userAgent = navigator.userAgent || navigator.vendor || window.opera;

        // Windows Phone must come first because its UA also contains "Android"
        if (/windows phone/i.test(userAgent)) {
            return "windows-phone";
        }

        if (/android/i.test(userAgent)) {
            return "android";
        }

        // iOS detection from: http://stackoverflow.com/a/9039885/177710
        if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
            return "ios";
        }

        return "unknown";
    }

    var os = getMobileOperatingSystem()

    if (os === "android") {
        window.location.replace("https://play.google.com/store/apps/details?id=cl.emilym.sinatra");
    } else if (os === "ios") {
        window.location.replace("https://apps.apple.com/au/app/sinatra-for-canberra/id6739419456");
    } else {
        console.log("Unable to determine app store for userAgent " + (navigator.userAgent || navigator.vendor || window.opera));
    }
</script>