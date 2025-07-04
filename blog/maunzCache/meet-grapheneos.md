# Meet GrapheneOS

*2025-07-04*

While I am silently reading a book about [Human-Centered Programming Languages](https://bookish.press/hcpl), there is even more going on. My mind was struggling how to summarize all the details of what is coming next, so i try to be brief about it for your reading pleasure.

## Inception

Since [Windows 10](https://endof10.org/) was "deprecated" I started using [Arch Linux](https://archlinux.org/), which runs for more than circa two years on my gaming computer. I already tried that around 2014, but it didn't work out smoothly. Its in a much better state now. Highly recommended to switch to any Linux distribution that serves a KDE Plasma 6 installation and comes a >=6.12 kernel.

Beginning of 2025, I started to hate my Google Pixel phone as [weird updates](https://support.google.com/pixelphone/answer/15701861) started to happen with older phones. This week we got [the AI overlord call](https://tuta.com/blog/google-gemini-ai-email), which will to the [same bad stuff Microsoft Recall does](https://doublepulsar.com/microsoft-recall-on-copilot-pc-testing-the-security-and-privacy-implications-ddb296093b6c). I can probably handle the AI on WhatsApp, because I can't drop that messenger yet, but I will do anything to add more privacy to my life. Take this blog as a double edged sword :D

The decision was to move to another phone as soon as Google gives me a reason and install sweet Linux with Waydroid on it.

Around May I started [the Cyber-Cleanse](https://www.optoutproject.net/the-cyber-cleanse-take-back-your-digital-footprint/), but haven't gotten very far. I needed more motivation. And then [PewDiePie happened, with The Primeagen reacting](https://www.youtube.com/watch?v=R3blSsMfMwU) to it. While I never succumbed to famous people, this got me. On the same day (yesterday) I started backing up my phone and installed [GrapheneOS](https://grapheneos.org/). I did it without knowing what it was or how it worked - pretty stupid. Luckily, its exactly what is wanted.

Here is my ride with it. For you <3

## Preparations

I have moved a lot of smartphones due to having devices for work which were available for private usage. Previously, all the data was backuped in Google Services (proabably Google One?) or I would be able to move the data directly using USB-C. Not this time though. It was time for so good old manual backup.

Here is a few questions you should ask yourself before starting anything:

- Where are my passwords stored and do I need to move them to a safe place? There is a [good approach figuring that out](https://www.optoutproject.net/data-roadmap/) with the mentioned Cyber-Cleanse.
- Do I have backups of my MFAs?
- Have I used passkeys? ([Don't do it!](https://fy.blackhats.net.au/blog/2024-04-26-passkeys-a-shattered-dream/) Really, [you shouldn't do it!](https://arstechnica.com/security/2024/12/passkey-technology-is-elegant-but-its-most-definitely-not-usable-security/))
- Is my banking app supported? (Check [here](https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/))
- Is there anything bound to my device that I need to reset first or have another way of accessing it?
- Do I have a backup of my messengers? (Consider you might not want them to access your Google account!)
  - Are there other apps that I need to manually backup?
- Is there any data that I need to have secure copy of?
- Do I have any devices connected to my smartphone (e.g. smartwatch)?
- Can I clean up?
- Is there anything from Google (Pixel) I really like or rely on?

At least that was, what was interesting to me. Interestingly, most of the questions were already solved or easy solveable with additional work though.

### Passwords and MFA

For my passwords, I already have a setup using [KeePass](https://keepassxc.org/) and [Syncthing](https://syncthing.net/). There is apps for both for the phone and computer, although syncthing needs [some extra attention on Android](https://github.com/Catfriend1/syncthing-android). It works quite well, which even convinced my partner to use it for private matters and work.

Regarding MFA (or 2FA), I have to admit using software TOTP mostly by Google Authenticator. Simply because I was to lazy to move to the better [FreeOTP+](https://github.com/helloworld1/FreeOTPPlus), which I currently use for work only. Both apps allow me to do an export. While the Google version felt more secure, it also was the worse to restore...

### App settings

One thing I can tell you straight to the face: You will have to reconfigure everything!

That is always true when moving devices and installing another OS, even if its also Android, is the same thing. You want to have screenshots of all your settings. I highly recommend to go through all apps you commonly use and backup any information you can. I didn't and that was kind of stupid.

In the end I decided, that I can remove apps I simple had for getting virtual goodies.

### Google Pixel features

You have to be aware of that you might not be able to use some specific Google Pixel features any more. [Google decided to release Pixel related code publicly anymore](https://9to5google.com/2025/06/12/android-open-source-project-pixel-change/), which might have an impact on some thing you would like to use.

### Backups

This one is kind of easy to achieve. The simplest thing you can do is a file backup by putting an USB cable into the phone and connect it to a computer. Copy whatever you want to keep, which is not app related, such as pictures, movies or music.

If you want to also have an backup for your apps and contacts there is a tool you can use: [open-android-backup](https://github.com/mrrfv/open-android-backup). It will basically save everything, except your app and device settings.

It require as bit of technical expertise or at least the will to try it. Its not hard. Follow the instructions of the README file and you will be good. When running the script, you will be guided through all steps.
When running the tool, be super sure that you have enough space on the hard drive where you are running the tool. It will create a temporary folder in its installation directory which contains your devices files as long as the backup process takes. Also, it is not fast. The more data, the longer it takes.  
The data will be packaged and secured by a password which you should "write down" for the recovery later.

## Moving to GrapheneOS

If you have access to a system that has:

- A Chromium based browser (Chromium, Chrome, Brave, ...)
- USB-C port or at least USB 3.x compatible USB-A port
- An USB 3 cable compatible with your phone and computer

You should make use of [the guided WebUSB installation](https://grapheneos.org/install/web). It is really good and straightforward and you do not need to understand any technical details. Just be sure that you can read and comprehend what you read.

If you are at the step **Verifying installation** you are largely done with the installation. Congrats! You have now a secure phone. If you haven't yet, you should [read why it is secure](https://grapheneos.org/features).

## Restoring open-android-backup backup

The first time you boot to GrapheneOS, it is pretty similar to a normal Android device, except that everything looks shitty. You should configure your defaults first and then got to the included App store and download the **Google Play Store** and **Googly Play services** apps. You will need those, except you decided to start from new and de-google everything. I respect that!

After you set up the defaults you are comfortable with plug back the USB cable and connect it to the device where your backup resides. Run the script of the open-android-backup again, but this time select **Restore**. It will ask you for the location of your backup file, password and what you want to restore. This will take as long as the backup so consider waiting for 1 to 2 hours.  
It might happen that apps cannot be installed because of missing features. In that case you have to look out for missing apps or even consolidate the [Google Playstore](https://play.google.com/apps).

After that:

- all your backuped apps are installed on the device
- all contacts should be in your phone book
- all your files are back on the device

However, there is work for you to do now!

GrapheneOS extends the permission handling so that you can decided to remove all (!) permissions from an app. By default (stock Android), every app will get access to Network and Sensor capabilities. The backup tool will install your apps the same way. So you should go through all of them and remove the permissions, unless you know you need them.  
For the restored files, they will be placed into a special directory called `Storage`. You might need to move those files up a directory. Bear in mind that the installed File tool cannot merge directories, it might be easier to move those files when connected to a computer.

Actually, you are done now. Yay! You are all good and ready for more time configuring everything the way it was before.

Setting up everything might not be easy, because you will need to give more granular permissions to apps. GrapheneOS tries its best to help you with notifications. You can do it though!

## Getting FOSS apps

If you don't want to reinstall all the vendor apps, then you have to get another app store on your device. The most famous one is [F-Droid](https://f-droid.org/) and for the hackers among us [Obtainium](https://obtainium.imranr.dev/) get you things right up from the source.

For vendors, [Fossify](https://github.com/FossifyOrg) has a good amount of apps that are open source and bring you back feature you might want.

## Connecting a smartwatch

There is one thing I want to point out, because it was super frustrating to me. If you happen to have a Google Pixel Watch, I am sorry for you. I am guilty of this and it really sucks.  
It was one of the worst buying decision I ever took, but I will keep the watch until I can replace the watchOS there as well.

What you should now: You will have to reset it back to factory settings.

Maybe that is not true for you, but my generation 1 watch would simply refuse to work. I knew that it was a problem when I switched to a new device, but didn't expect it to be so miserable this time. I was wrong :(

## New feature you should know of

If you are at this point of reading and - just as I - did have a look into the feature set of GrapheneOS, here is a small toplist of things I discovered and really like.

### Multiple profiles

I don't think I have every seen that on a Pixel device, besides when the sandbox for work was activated, so it was new to me. You can now configure to have multiple profiles or users on the device. Heck, even have a guest account that resets itself.

It adds a layer of security, which is super awesome. The way to switch profiles is not too intuitive, but it works. If you want to have a profile for e.g. work, gaming or safe browsing you should configure it.

Be aware that you will need to fully reconfigure everything per profile. With that you could even share a device with your partner.

### Power saving everywhere

When configuring everything, my battery was starting to empty itself pretty quickly. However, i noticed afterwards that the overall consumption decreased as a lot of tasks are not running in the backgroung that previously were running. I have yet to figure out, whether it impacts any app, but right now I think all is good.

### TBD

While I am incepting into this new universe, I will probably update this blog entry a few times. Also kill those typos.

---

Hope that was a bit of an inspiration to you.

~maunz