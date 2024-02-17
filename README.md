(in)Complete Guide to Keitais (in progress)

When i got my keitai, i felt like i missed a lot of information and had to figure myself out, so I decided to start writing the things I did so others could have it easier. (I usually delete my accounts after a couple days, but I'll leave this one active just to update this guide with more info as I discover new things)

I'm assuming you have adb installed, if you don't, install it. there's lots of info about it

# To enable adb on the phone

1. Go to settings
2. Click on "About phone"
3. Click multiple times on "Build number" until a message pops saying "you are a developer"
4. Go to "More settings"
5. Scroll down to "Developer options"
6. Enable USB debugging

# To replace the Email Key shortcut (and others) with Messages w/o losing functionality:

1. Open adb and type "adb shell pm disable-user jp.kyocera.fpmail"  (jp.kyocera.fpmail is the email app package name)
2. Go to KeyMapper (install it, if you haven't already)
3. Add an action and set the trigger
4. On the top of the display, bellow "trigger", there's a box that says F1 (it changes according to the key you pressed)
5. Click on the 3 dots on that box and check on "do not remap"
6. Set the trigger to double press or to long press (you can have different functions for both)
7. Remember to save the action (bottom right icon)

Don't set it to "Short Press" or there will be issues

Extra (package names to replace other buttons):

* TV - jp.co.fsi.fs1seg
* Browser - com.android.browser
* Camera - [](http://jp.kyocera.camera)

Note:

* You will have to find alternative apps, as the apps you disable will, of course, be disabled

Personal Keys:

Email Key:

* Messages (double click)
* Whatsapp (long press)

TV key:

* Uber (double click)
* Bus Tickets (long press)

Browser key:

* Firefox Lite (double click)
* PC Mail (long press)

Camera:

* Camera (double click) -> i didn't disable it, no issues found so far
* QR Reader (long press)

# To use the regular notification bar

I got tired of using the Kyocera notifications (which are quite awful in my opinion), no i made the backspace button to be a shortcut to swipe down the regular notification panel

1. Go to the KeyMapper app i mentioned above
2. Add action and set the backspace as a trigger
3. Go to the 3 dots and select "do not remap"
4. Check the "Long Press" box
5. Navigate to action and pick "swipe screen"
6. Fill **start X** and **start Y** with **0** and **end X** and **end Y** with **1000**
7. Remember to save the action (bottom right icon)

Note: to edit the notification bar use scrcpy (mentioned in Extra Tips)

# To use Gmail:

1. Enter the website "https://myaccount.google.com/security"
2. Go to "two step validation"
3. Scroll down and click on "app passwords"
4. Create an app name and copy the password that is displayed
5. Open ADB and use the command "adb shell input text password", replacing "password" with the one google displayed
6. Enter the email as well and click "next" until it gets to your inbox

# To make email UI better:

1. Open the email app and pick "PC Mail"
2. Click on menu and go to "Settings"
3. Pick "General Settings" and check "Auto-fit messages" and turn on "Include original text"

# To use Google Authenticator (Keeping the linked accounts):

1. Install Google authenticator through adb
2. Open it and click on "use without account"
3. Go to your android phone, click on "Transfer accounts" and "Export accounts"
4. Go to adb and use the command "adb shell wm density 160"
5. On the kyocera device, click on Transfer accounts and "Import accounts"
6. Follow the steps
7. Once completed, go to adb and use "adb shell wm density reset"

# To use an SD Card bigger than 32gb:

1. Download fat32format (just google it)
2. Pick your driver and click format
3. If it warns you that your driver is being used by another app, you have to open the task manager and kill file explorer

* Please be cautious and select the right driver

# To change the apps on the App Drawer:

1. Open the app drawer and click on the Email key (Menu)
2. Click on Layout and select the last option
3. You can now edit the apps
4. Tip: the "Custom Menu" is on the "List" when adding an app

# Other Tips:
 
* If you fill the APN settings and the page is still blank when you save it, you need to ask your carrier for appropriate APN values.
* Setting Sub Display font to small will show the date at the left of the clock (credits to someone, but I'm not sure where I saw it)
* [scrcpy ](https://github.com/Genymobile/scrcpy)allows you to control the phone on the PC, making it easier for some tasks
* **adb shell input text "text"** allows you to write in fields with the console (replace "text" with desired text)
* **adb shell wm density 160** will fix any issues with apps that are not compatible with small screens, but you have to use **adb shell wm density reset** once you leave the app (you can also install [resolution changer](https://apkcombo.com/pt/resolution-changer/com.draco.resolutionchanger/download/apk) to get similar results without a PC)
* When writing something, pressing the camera key will make the letter go to the previous one, and if you press it after clicking the letter for the first time, it will switch to the assigned number (e.g. pressing "1" will write "a", you click on the camera key and it turns into "1"

I'll try to update this whenever i can :)
