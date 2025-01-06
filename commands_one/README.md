### (1) . Flutter : Generate SHA1, SHA256 Key For Firebase

When working with firebase, if you adding your project manually ( not using the flutter cli ), if you need to use features, Google Sign in, phone verification you would need to enter your project's sha-1 and sha-256 key. 


####  -- In your android folder, open "gradlew"  Open in Terminal -

paste the command ```gradlew signingReport``` windows or powershel or ``` ./gradlew signingReport```  For Unix based system like mac

Wait for the command to finish running, the output will included the sha1 and sha256


### (2) . FVM Flutter CLI

A rare case wher flutterfire configure is not working

```fvm flutter pub global run flutterfire_cli:flutterfire configure```


```fvm flutter pub global run flutterfire_cli:flutterfire configure --project=project_name --platforms=android,ios```    


### (3) . Converting File to Base64


convert a file to base64 and export it into another file ( config_keys_base64 )
```base64 -i config_keys.json -o config_keys_base64.txt```

