# Android-Firebase Authentication Demo App
![firebase-logo](https://s.appbrain.com/static/201706261945530/blob/sdk-logos/firebase.png)


Firebase for Android basic Sign Up


![firebase_signup](https://cloud.githubusercontent.com/assets/11635523/20765373/a50e7d9c-b6f7-11e6-8473-32820c06cb2a.gif)


![auth 2 registered user](https://cloud.githubusercontent.com/assets/11635523/20765364/9e6420e6-b6f7-11e6-9ab2-133bb313a6ea.JPG)

Basic useful feature list:

 * Allow user to sign up to the application
 * The user's information is dispalyed via Firebase Auth


Dependencies Used in the App

```gradle
 compile 'com.google.firebase:firebase-auth:10.0.1'
```

Apply this plugin to the **build.gradle(Module:app)** after *dependnecies*

```gradle
apply plugin: 'com.google.gms.google-services'
```

In your **build.gradle(Project:FirebaseAuthDemo)** or Poject folder add this classpath in the *dependencies*
```gradle
 classpath 'com.google.gms:google-services:3.0.0'
```



Permissions used in the App

Add this permission in you **AndroidManifest.xml** file
```xml
 <uses-permission android:name="android.permission.INTERNET"/>
```

In order to use Firebase you will need to initialize the firebase auth object. In your **MainActivity**

```java
FirebaseAuth firebaseAuth;
```
Next in your onCreate method you will create the object for firebase.

```java
 firebaseAuth = FirebaseAuth.getInstance();
```
You will need to create method for the *firebaseAuth* **creatUserWithEmailAndPassword()**

```java
     firebaseAuth.createUserWithEmailAndPassword(email, password)
                .addOnCompleteListener(this, new OnCompleteListener<AuthResult>() {
                    @Override
                    public void onComplete(@NonNull Task<AuthResult> task) {
                        //checking if success
                        if(task.isSuccessful()){
                            //display some message here
                            Toast.makeText(MainActivity.this,"Successfully registered",Toast.LENGTH_LONG).show();
                        }else{
                            //display some message here
                            Toast.makeText(MainActivity.this,"Registration Error",Toast.LENGTH_LONG).show();
                        }
                        progressDialog.dismiss();
                    }
                });

```
Additional information available via [Firebase](https://firebase.google.com/docs/auth/android/start/) website
![firebase-android](https://image.slidesharecdn.com/random-170509165044/95/secon2017-android-things-google-weave-6-638.jpg?cb=1494351640)
