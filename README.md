OwnOTA
-------
A very simple OTA checker with Android Settings look and feel.

How it works
------------
It parses the OTA xml file that you put in your file hosting and compares the version number with the local one.
If the version is newer, it notifies the user for a new ROM update.

How to use
----------
* Prepare the OTA xml file. Use this [template](https://raw.githubusercontent.com/OwnROM-Devices/OTA/own-n/OwnDroid.xml).
* Upload it to your file hosting and create a hot link of it
* Copy the [ota_conf template](https://raw.githubusercontent.com/OwnROM/packages_apps_OwnOTA/own-n/examples/ota_conf) to app/src/main/assets folder
  * If you are buiding this app as part of the ROM, you need to copy ota_conf in the android root folder.
  * The Android.mk will pick it up and copy it to app/src/main/assets folder automatically.
* Replace the "ota_url" with your OTA xml hot link
* Define how OwnOTA should know about the "version". The version must be parseable to a date.
  * Usually, the version is a part of a build name. For example, the 20160515 in the OwnROM-OFFCIAL-Nightly-v3.0-angler-20160515.zip
* Adjust the OTA configuration according to your build name on how should OwnOTA parse the version
  * Find a key in build.prop that represents the SlimSaber-bacon-5.0.2-20150426 and set it in the "version_name"
  * Set the delimiter in "version_delimiter" to "-"
  * Set the date format in "version_format" to "yyyyMMdd"
  * Set the position in "version_position" to "5" (zero based)
* Find a key in build.prop that represents your device name and set it in the "device_name"
  * OwnOTA will search this device name in the OTA xml file

Most guys can skip the below part
---------------------------------
Define how OwnOTA should know about the "version". The version must be parseable to a date. Usually, the version is a part of a build name. 
For example, the 20170514 in the OwnROM-OFFICIAL-v4.0-angler-20170514. Adjust the OTA configuration according to your build name on how should OwnOTA parse 
the version Find a key in build.prop that represents the OwnROM-OFFICIAL-v4.0-angler-20170514.zip and set it in the "version_name" Set the delimiter 
in "version_delimiter" to "-" Set the date format in "version_format" to "yyyyMMdd" Set the position in "version_position" to "4" (zero based) Find a key in 
build.prop that represents your device name and set it in the "device_name" OwnOTA will search this device name in the OTA xml file


For OwnROM maintainers
-----------------------
* Sync OwnOTA or wait till full sync
* go to [HERE](https://github.com/OwnROM-Devices/OTA/tree/master/Maintainers) and make a xml file with your name or nickname
* Copy the content of [OwnDroid.xml](https://raw.githubusercontent.com/OwnROM-Devices/OTA/own-n/OwnDroid.xml) and make the references to your rom, links and stuff
* Save it
* Click on "Raw" and save the link
* Go to [HERE](https://raw.githubusercontent.com/OwnROM/packages_apps_OwnOTA/own-n/examples/ota_conf) and copy the content a file named "ota_conf" placed in the OwnROM source top folder.
* Replace the "ota_url= " with your own link you saved from the raw xml url
* and your done
* Now make a clean build

Credits
-------
* [SlimRoms team](http://Slimroms.net/)
  * For the original idea of the SlimCenter and app icon
* [CommonsWare Android Components](https://github.com/commonsguy/cwac-wakeful)
  * For the wakeful intent service that is used in this app

Screenshots
-----------
<img alt="Screenshot"
   width="270" height="480" 
   src="https://raw.githubusercontent.com/SlimSaber/packages_apps_SlimOTA/lp5.0/screenshots/Screenshot_20150505_1317.png" />
