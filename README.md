# DEMO
[![](https://jitpack.io/v/arhanashik/base.svg)](https://jitpack.io/#arhanashik/base)

## What's it
This is a simple framework for my projects for setting things up before staring any project. It's my own structure which
I follow for my projects. Common dependencies and helper files are added for faster development
 
## Installation
### Using with gradle
1. **Step 1** Add it in your root build.gradle at the end of repositories:
```
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

2. **Step 2** Add the dependency to your app level build.gradle
```
dependencies {
    implementation "com.github.arhanashik:base:latest-version"
}
```

## Using as a module
1. Clone the repo
2. Change the package name and applicationId
3. Change the git remote address

**That's it!** Start development!

## Api and functionality:
1. Image Cropper(UCrop)
Add this into application tag to manifest.
```
<activity
    android:name="com.yalantis.ucrop.UCropActivity"
    android:screenOrientation="portrait"
    android:theme="@style/Theme.AppCompat.Light.NoActionBar"/>
```
Then call ImageUtil().crop(activity, imageUri). The cropped Result will be in the onActivityResult:
```
if (resultCode == RESULT_OK && requestCode == UCrop.REQUEST_CROP) {
    if(data != null) {
        val resultUri = UCrop.getOutput(data)
    }
} else if (resultCode == UCrop.RESULT_ERROR) {
    if(data != null) Timber.e(UCrop.getError(data))
}
```