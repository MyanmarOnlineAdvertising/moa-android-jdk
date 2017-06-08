# MOA-Android-Sdk
MOA Android SDK to tap into MOA Ad Network.

# Register at Myanmar Online Advertising as Publisher to get the ad unit code
https://moa.com.mm/register

# How to Add library
1. Download [moaadssdk.arr](https://github.com/MyanmarOnlineAdvertising/moa-android-jdk/releases/download/v0.1/moaadssdk.aar)
 and place it under the libs folder
2. add the following code to project build.gradle file
  ```groovy
    flatDir {
      dirs 'libs'
    }
   ```
3. add the following code in Application build.gradle and sync with gradle
  ```groovy
   compile(name: 'moaadssdk', ext: 'aar')
   compile 'com.squareup.moshi:moshi:1.5.0'
   compile 'com.squareup.okhttp3:okhttp:3.8.0'
   ```
# Usage for Banner Ads and FullScreen Ads
 adsUnitId need to replace with Ads Unit ID from your publisher project at www.moa.com.mm
 
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
   
   Fullscreen Ads can be implemented as the following:
   adsUnitId need to replace with FullScreen Ads Unit ID 
   from your publisher project at www.moa.com.mm
   
   ```java
      int showPerTime =2;
      MoaAds moaAds = new MoaAds(this);
      moaAds.initFullScreenAds(showPerTime, "fid_xxxxxxxxxxxxx");
   ```
   
  with the above example Fullscreen ad will be shown whenever user enters the app the second time.
  
  # Ads Listeners for MoaAdsView
  You can also listen to Ads request status with MoaAdListener as the following
  `int code` is Http Status code, 400 means error and 204 means rate limited.
  
  ```java
  moaAdsView.addAdsListener(new MoaAdsView.MoaAdListener() {
      @Override public void onAdsLoaded(int code) {
        //create your own logic
      }

      @Override public void onAdsFailed(int code) {
        //create your own logic
      }
    });
  ```  
  
  # MoaAdsView with RecyclerView
  You can also use MoaAdsView with the RecyclerView as the following,
  
  ```java
    PeopleAdapter mPeopleAdapter = new PeopleAdapter();
    mPeopleAdapter.setItems(mList);
    MoaAdsAdapter moaAdsAdapter = new MoaAdsAdapter(mPeopleAdapter, this, "aid_xxxxxxxxx");
    mRecyclerView.setAdapter(moaAdsAdapter);
  ```
  
  adsUnitId needs to replace with Ads Unit ID from your publisher project at www.moa.com.mm

  # Example Projects
  [MoaAds Example](https://github.com/MyanmarOnlineAdvertising/moa-android-examples/tree/master/moa-android-sdk)
  
  
  # Help
  
  Report a bug by creating an issue on our github repo.
  
  Also [contact us](https://www.moa.com.mm/about) if you have any difficulties implementing our ad jdk.
  
  
  # MOA - The ad network that helps you earn more while you focus on creating better contents.
