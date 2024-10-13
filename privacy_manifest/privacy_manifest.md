
# TMS-91108: Invalid privacy manifest - The PrivacyInfo.xcprivacy file from the following path is invalid: “Frameworks/Reachability.framework/ReachabilitySwift.bundle/PrivacyInfo.xcprivacy”. - Flutter


After my build was approved by appstore,  I got an email from appstore saying soemthing was wrong with my build and that i must fix before 12 Nov 2024 else they will start rejecting any new build  published which still has that error.

[Privacy Manifest](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files?language=objc) is a file used by apple to describe data your app or third party sdk collects. You can read more about it


## Cause

In my particular use case, it wasn't my app causing this error but a third party library. So i had to locate the library ( Which i did ). 

## Solution 
I was using an older version of the package which hadn't supported the privacy manifest and luckily i was no longer in need of the package so i just had to remove it.


## Locate The Library
To locate the library, check your ```podfile.lock```, In your podfile.lock check what library is referencing reachability.

if found you can check if there's an updated version of the package in pub.dev or notify the author of the package

