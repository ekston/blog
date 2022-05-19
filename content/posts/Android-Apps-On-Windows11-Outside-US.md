---
title: An easy way to run Android apps on Windows 11 - outside of the US
date: 2022-05-19
draft: false
---

  
In October 2021, Microsoft announced the support for [Android apps on Windows 11](https://blogs.windows.com/windows-insider/2021/10/20/introducing-android-apps-on-windows-11-to-windows-insiders/). What was then a feature in preview for Windows Insider, has in the meantime been, .... well in all honesty, I have no idea what the status is. It has gotten awfully quiet in that area. 

Nevertheless, certain aspects of it I find very interesting. Out of professional curiosity, I tried to install it on a Windows 11 device. The official guidance relies on the Amazon store and an american account. So I had to find my way around that. There are plenty of tutorials to achieve sideloading -  most of them are painfully cluttered with ads. So I'll quickly recapitulate the steps[^1]:
1. Check the [device requirements](https://support.microsoft.com/en-gb/windows/install-mobile-apps-and-the-amazon-appstore-f8d0abb5-44ad-47d8-b9fb-ad6b1459ff6c)
2. Go to [store.rg-guard.net](https://store.rg-adguard.net/)[^2] - paste 9p3395vx91nr - pick ProductID from the left dropdown, and Slow from the right one - download the large MSIXBundle (in my case, the last entry on the list)
3. Start PowerShell as admin and run Add-AppxPackage -Path "path-to-the-downloaded-appx"
4. Download and extract [the latest Android platform tools for Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
5. Start Windows Subsystem for Android - activate the developer options, start the files app and copy the IP of the WSA.
6. Go to [AuroraOSS](https://auroraoss.com/) and download the AuroraDroid store to the platform-tools (folder of the Android platform-tools you extracted in step 4).
7. Start CMD as admin and cd into the platform-tools directory. Connect to Android with the command *adb connect IP*
8. Install the apk file with the command *adb install apk-name*

Voilà. 

{{< figure library="true" src="/img/aurora.png" title="Aurora OSS store" lightbox="false" >}}


**Disclaimer** You are now downloading software from Aurora OSS. Decide for yourself if you trust them, or want to wait for the official version with Amazon outside of the U.S. 

[^1]: [This guide](https://www.windowscentral.com/how-sideload-android-apps-using-wsa-windows-11) worked in my case and adds a bit more context and screenshots to the process.
[^2]: Maybe also use a browser with some ad blocking.