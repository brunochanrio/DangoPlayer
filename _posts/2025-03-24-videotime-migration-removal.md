---
title:  "Removal of the migration code that allowed migration from the obsolete DangoPlayer (formerly VideoTime and TubiLeap) to modern DangoPlayer (formerly DangoPlayer Uni)"
date:   2025-03-24 15:34:00
categories: update
badges:
 - type: warning
   tag: feature removal
---
<img alt='Obsolete DangoPlayer to Modern DangoPlayer migration removal' width='700' src='https://brunochanrio.github.io/DangoPlayer/news/img/VideoTimeToDangoMigrationRemoval.png'/>

We are announcing that we decided to remove the code that allowed migration of IPTV Lists from the obsolete DangoPlayer app (formerly known as VideoTime and TubiLeap) on Android and the obsolete DangoPlayer TV app on Android TV and Google TV to the modern DangoPlayer app (formerly known as DangoPlayer Uni), this is doing as a part of a strategy to remove unused and obsolete code to modernize the app

<!--more-->

## What happened to the obsolete DangoPlayer and DangoPlayer TV apps?
In 2023, we figured that developing DangoPlayer for mobile devices and TVs in separated codebases (one for mobile devices and other for TVs) was difficult, also because app updates doesn't came at the same time for both versions

Due to this, we merged the then-existing DangoPlayer and DangoPlayer TV codebases into a single and unified codebase for both mobile devices and TVs, resulting in a single app that worked on both mobile devices and TVs, known as DangoPlayer Uni (the Uni in the name has been added to prevent confusion with the now-obsolete DangoPlayer and DangoPlayer TV apps, this is because the DangoPlayer Uni name was used as a transition name)

On the last version of the obsolete DangoPlayer and DangoPlayer TV apps (**2023.7.12poochy_rev2**) we implemented a warning message that informed about the deprecation of the then-deprecated DangoPlayer and DangoPlayer TV apps in favor of the then-new DangoPlayer Uni, that appeared every time the obsolete DangoPlayer and DangoPlayer TV apps are launched on the device

<img alt='Obsolete DangoPlayer deprecation message at launch' width='400' src='https://brunochanrio.github.io/DangoPlayer/news/img/VideoTimeDeprecationMessage.png'/>

To facilitate users of the obsolete DangoPlayer and DangoPlayer TV apps to migrate to the then-new DangoPlayer Uni app, we implemented a migration code in both the obsolete DangoPlayer and DangoPlayer TV apps, and the then new DangoPlayer Uni app, the migration code on the obsolete DangoPlayer and DangoPlayer TV apps takes the IPTV lists that are added on the obsolete DangoPlayer and DangoPlayer TV apps and passes the taken lists to the migration code on the DangoPlayer Uni app, while the migration code on the DangoPlayer Uni app readds the taken IPTV lists to the new app 

## How the migration codes worked:
<img alt='Obsolete DangoPlayer to DangoPlayer Uni Migration' width='700' src='https://brunochanrio.github.io/DangoPlayer/news/img/VideoTimeToDangoMigrationCurrent.png'/>

1. When launching the DangoPlayer Uni app, the app would check if the obsolete DangoPlayer app on mobile devices or the obsolete DangoPlayer TV app on TVs are installed and the migration code of the obsolete app is present (this required the last version of the obsolete DangoPlayer and DangoPlayer TV apps, which is **2023.7.12poochy_rev2**)
2. If the obsolete DangoPlayer/DangoPlayer TV app is detected, the migration code of the obsolete app are loaded
3. Once the migration code of the obsolete app are loaded, the code takes the existing IPTV lists on the obsolete app and then passes the taken IPTV lists to the migration code of the new app and then the migration code of the new app is loaded
4. Once the migration code of the new app are loaded, the code would add the IPTV lists taken by the obsolete app and then adds the taken IPTV lists to the IPTV list database of the new app

Here is a video demonstration on how the migration codes of both the obsolete DangoPlayer app and the modern DangoPlayer app works:

<video controls width="350">
  <source src="https://brunochanrio.github.io/DangoPlayer/news/vid/VideoTimeToDangoMigrationDemo.mp4" type="video/mp4" />
  <img alt='Unsupported browser' width='450' src='https://brunochanrio.github.io/assets/HTML5VideoUnsupported.png'/>
</video>

In the video demonstration we used the last version of the obsolete DangoPlayer app (**2023.7.12poochy_rev2**) and the current version of the modern DangoPlayer app (**5.0freya**), which is the last version of the modern DangoPlayer to include the migration code, as the next version of the modern DangoPlayer (**6.0usagi**) will remove the migration code completely

## The end of the transition
In 2024, with the release of the version **2.0hangyodon** we renamed DangoPlayer Uni to simply DangoPlayer, which now doesn't make confusión with the obsolete DangoPlayer and DangoPlayer TV apps, as the number of users of the obsolete apps has decreased with the removal of the obsolete apps from the Google Play Store and the migrations to DangoPlayer Uni, marking the end of the transition from the obsolete DangoPlayer and DangoPlayer TV apps to the modern DangoPlayer app

However, despite the transition has ended, the migration code of the DangoPlayer Uni app that added the IPTV lists taken by the obsolete DangoPlayer and DangoPlayer TV apps to the DangoPlayer Uni app still remains today on the modern DangoPlayer app as of the latest version **5.0freya**, but not for long time

## The removal of the DangoPlayer Uni migration code
We planned to remove the DangoPlayer Uni migration code from the modern DangoPlayer app beginning with the next version (6.0usagi) which is currently in development, as the number of users of the obsolete DangoPlayer and DangoPlayer TV apps continues to decrease, the migration code now are no longer needed

## What means the removal of the DangoPlayer Uni migration code from the modern DangoPlayer app for remaining users of the obsolete DangoPlayer and DangoPlayer TV apps?
For the remaining users of the obsolete DangoPlayer and DangoPlayer TV apps, with the removal of the DangoPlayer Uni migration code from the modern DangoPlayer in the next version **6.0usagi**, when the next version **6.0usagi** of the modern DangoPlayer is released on the Google Play Store, remaining users of the obsolete DangoPlayer and DangoPlayer TV apps that still have the obsolete DangoPlayer and DangoPlayer TV apps installed on their devices and their devices have Android 9 or later could still download the modern DangoPlayer app from the Google Play Store by clicking on the "Get DangoPlayer Uni" button on the deprecation message of the obsolete DangoPlayer and DangoPlayer TV apps, but even after downloading the modern DangoPlayer app, if the downloaded version is **6.0usagi** or later, when launching the modern DangoPlayer app and give the Storage access permission (or the Photos and Videos access permission on Android 13 and later), the migration code of the obsolete DangoPlayer and DangoPlayer TV apps would no longer be loaded, and the modern DangoPlayer app would start as normal without migrating the IPTV lists from the obsolete DangoPlayer and DangoPlayer TV apps

## How can distinguish the obsolete DangoPlayer and DangoPlayer TV apps from the modern DangoPlayer app?
Here are a way to distinguish the obsolete DangoPlayer and DangoPlayer TV apps from the modern DangoPlayer app, by checking the icon differences and the package name

<table>
  <thead>
    <tr><th align="left">Icon</th><th align="left">Corresponding app</th></tr>
  </thead>
  <tbody>
    <tr><td nowrap><img alt='Obsolete DangoPlayer Icon' width='64' src='https://brunochanrio.github.io/DangoPlayer/news/img/ObsoleteDangoIcon.png'/></td><td>The icon of the obsolete DangoPlayer (<b>com.aleapps.videotime</b>) and DangoPlayer TV (<b>com.aleapps.videotimetv</b>) apps. Notice that the icon has a darker solid purple background, the Dango colors are Light Pink, Light Purple and Light Blue, and the Dango stick color are Light Amber</td></tr>
      <tr><td nowrap><img alt='Initial Modern DangoPlayer Icon (DangoPlayer Uni)' width='64' src='https://brunochanrio.github.io/DangoPlayer/news/img/UniDangoLogo.png'/></td><td>The initial icon of the modern DangoPlayer (<b>com.brunochanrio.dangoplayeruni</b>) app, which are used on all <b>DangoPlayer Uni</b> branded versions until <b>1.7nezuko_rev1</b>. Notice that the icon has a dark solid purple background, the Dango colors are Light Pink, Light Mint Green and Light Purple, and the Dango stick color are Light Amber</td></tr>
    <tr><td nowrap><img alt='Current Modern DangoPlayer Icon' width='64' src='https://brunochanrio.github.io/DangoPlayer/news/img/CurrentDangoIcon.png'/></td><td>The current icon of the modern DangoPlayer (<b>com.brunochanrio.dangoplayeruni</b>) app, which are used on the current version (<b>5.0freya</b>). Notice that the icon has a colorful gradient background composed of Pink, Purple, Blue and Mint Green colors, the Dango colors are Light Pink, Light Mint Green and Light Purple, and the Dango stick color are Light Amber</td></tr>
    <tr><td nowrap><img alt='New Modern DangoPlayer Icon' width='64' src='https://brunochanrio.github.io/DangoPlayer/news/img/FutureDangoIcon.png'/></td><td>The new icon of the modern DangoPlayer (<b>com.brunochanrio.dangoplayeruni</b>) app, which will begin to be used starting with the next version (<b>6.0usagi</b>) as part of the new DangoPlayer rebranding. Notice that the icon has a colorful gradient background composed of Pink, Mint Green, Yellow and Purple colors, the Dango colors are Light Pink, Light Mint Green and Light Yellow, and the Dango stick color are Light Purple</td></tr>
    
  </tbody>
</table>

## What means the removal of the DangoPlayer Uni migration code from the modern DangoPlayer app for new and existing users of the modern DangoPlayer app?
Nothing, the DangoPlayer Uni migration code was only used to transfer the IPTV lists from the obsolete DangoPlayer and DangoPlayer TV apps to the modern DangoPlayer app during the transition period, this means that the DangoPlayer Uni migration code is completely useless for new and existing users of the modern DangoPlayer app, including those who already migrated from the obsolete DangoPlayer and DangoPlayer TV apps to the modern DangoPlayer app

This is why we are removing the DangoPlayer Uni migration code from the modern DangoPlayer app beginning with the next version (**6.0usagi**)
