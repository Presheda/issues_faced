# (Android)** ERROR ** : Unable to read Dashboard config. Please confirm that your Branch key is properly added to the manifest. Please fix your Dashboard settings.

I was integrating deeplinking using [branch.io](https://branch.io/) when i encountered the above error on android

```
** ERROR ** : Unable to read Dashboard config. Please confirm that your Branch key is properly added to the manifest. Please fix your Dashboard settings.

Please follow the link for more info https://branch.app.link/link-settings-page
```

It said my dashboard was not configured even though i have correctly added the necessary files in my AndroidManifest


After hours searching and debugging every line, i found the root cause ( in my case of course )


###The Main Cause
```
AppTrackingStatus status = await FlutterBranchSdk.requestTrackingAuthorization();
```

I was calling the above method to request app tracking, the mistake was that i wasn't checking if the platform was iOS. 

The above method was only supposed to be called on iOS and not Android. But in my section of the code i forgot to add to check for platform 


##### Don't call the above method on android, do a platform check first


####
NOTE : This is only a short note on the above error and you might need to do further research is your use case is different