# moa-android-sdk
MOA Android SDK to tap into MOA Ad Network.


# How to Add libiary
1. Download moaadssdk.arr and place under the libs folder
2. add following code to Project build.gradle file
    flatDir {
      dirs 'libs'
    }
3. add the following code in Application build.gradle and Synce with gradle
   compile(name: 'moaadssdk', ext: 'aar')

