

# Flutter : Your scoped storage permission declaration needs to be updated.

---

I was publishing an android build using [codemagic.io](https://codemagic.io/) when the process failed with this error.

![Scoped storage error](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tax0qmb26ry4ozyb8945.png)

### Short Summary on Scoped storage
Of course the first thing i had to do was to research [scope storage](https://developer.android.com/training/data-storage#scoped-storage).

Scope storage is all about the android OS restricting the storage access your app has on the device. In earlier versions of the Android  OS, your app has storage access to wide number of locations/folder within the device. This unlimited storage access poses a threat as bad actors can take advantage of it hence the need to restrict it.

###The Main Cause
```
<uses-permission android:name="android.permission.MANAGE_EXTERNAL_STORAGE" />
```

In my case, having the above permission in my `AndroidManifest.xml` triggered the error

This permission is mostly provided to app such as file explorer. 

That does not mean it's a dead end if your app requires this permission. You would just have to update your permission ( Maybe by writing to the playstore review/policy team -  ). 

But for a lot of app use cases, you wouldn't need this permission.

The above permission is different from these two permission below and they don't trigger the error, 
```
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />

<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" /> 
``` 
####
NOTE : This is only a short note on the above error and you might need to do further research is your use case is different