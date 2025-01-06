### (1) . Flutter : Generate SHA1, SHA256 Key For Firebase

When working with firebase, if you adding your project manually ( not using the flutter cli ), if you need to use features, Google Sign in, phone verification you would need to enter your project's sha-1 and sha-256 key. 


####  -- In your android folder, open "gradlew"  Open in Terminal -

paste the command ```gradlew signingReport``` windows or powershel or ``` ./gradlew signingReport```  For Unix based system like mac

Wait for the command to finish running, the output will included the sha1 and sha256