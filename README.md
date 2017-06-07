# moa-android-sdk
MOA Android SDK to tap into MOA Ad Network.

#Register at Myanmar Online Advertising as Publisher
https://moa.com.mm/register

# How to Add libiary
1. Download [moaadssdk.arr](https://github.com/MyanmarOnlineAdvertising/moa-android-jdk/releases/download/v0.1/moaadssdk.aar)
 and place under the libs folder
2. add following code to Project build.gradle file
  ```groovy
    flatDir {
      dirs 'libs'
    }
   ```
3. add the following code in Application build.gradle and Synce with gradle
  ```groovy
   compile(name: 'moaadssdk', ext: 'aar')
   compile 'com.squareup.moshi:moshi:1.5.0'
   compile 'com.squareup.okhttp3:okhttp:3.8.0'
   ```
# Usage for BannerAds and FullScreen Ads
 adsUnitId need to replace with Ads Unit ID at your publisher project at www.moa.com.mm
 
  ```xml
   <com.zeta.moaadssdk.Views.MoaAdsView
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:id="@+id/moa_ads_container"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:gravity="center_vertical|center_horizontal|center"
        app:adsUnitId="aid_xxxxxxxxxxxxxx"
    />
   ```
   Fullscreen Ads can be used as the following:
   adsUnitId need to replace with FullScreen Ads Unit ID at your publisher project at www.moa.com.mm
   ```java
      MoaAds moaAds = new MoaAds(this);
      moaAds.initFullScreenAds(3, "fid_xxxxxxxxxxxxx");
   ```


