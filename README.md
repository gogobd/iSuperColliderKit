iSuperColliderKit (iSCKit)
=================

Broken English.

## OverView
"iSCKit" is SuperCollider on iOS7 later, it forked "supercollider iOS" project.

## Install
1. Download or Pull the project


### iSCKit (static libraries)

1. Launch iSCKit.xcodeproj using XCode
Location : [project root] > [platform] > [iSCKit] > iSCKit.xcodeproj


2. Select 'iSCKit' scheme
XCode launching, please select target 'iSCKit' scheme.


3. Run
It generate 'libsndfile', 'libscsynth' and 'libiSCKit' on [lib] direcotry.
Please make sure that generate 3 static library files above.
Location : [project root] > [platform] > [iSCKit] > [lib]


### iSCApp (iOS app)
This project is sample app using iSCKit. It is done getting ready to use iSCKit.


1. Launch iSCApp.xcodeproj using XCode
It need to already generate 'libsndfile', 'libscsynth' and 'libiSCKit'.
Location :  [project root] > [platform] > [iSCApp] > iSCApp.xcodeproj


2. Run
iSCKit must use iOS devices (cannot use simulator).
If this process succeed, iSCKit is available. 


3. Check Supercollider Log
Please make sure suppercollider log message on this app,
then select 'live' tab, iSCApp sound sine wave ( {SinOsc.ar()}.play ).



##  Setting Detail

1. Project Location
Project directory must be located same position of iSCKit directory like to iSCApp directory.


2. 'Header Search Path' (Build Setting)
Add [project root] > [editors] > [scapp] > [iphone] path.

ex. ../../editors/scapp/iphone


3. 'Library Search Path' (Build Setting)
Add [project root] > [platform] > [iSCKit] > [lib] path.

ex. $(PROJECT_DIR)/../iSCKit/lib


4. 'Objective-C Automatic Reference Counting' (Build Setting)
Set 'YES'.


5. 'PreProcessor Macros' (Build Setting)
Set 'SC_IPHONE' on 'Debug', and 'SC_IPHONE NDEBUG' on 'Release'.


6. 'Other Linker Flags' (Build Setting)
Add '-lsndfile -lscsynth -liSCKit'.


7. Copy and add 'SCClassLibrary directory' in iSCApp directory.
When you add this directory on xcode, please select 'Create folder reference'.


8. Add Frameworks.
AVFoundation.framework  
CoreMIDI.framework  
Accelerate.framework  
CFNetwork.framework  
CoreFoundation.framework  
CoreGraphics.framework  
AudioToolbox.framework  
MediaPlayer.framework  
UIKit.framework  
Foundation.framework  

