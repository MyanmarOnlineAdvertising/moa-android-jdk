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
   adsUnitId need to replace with FullScreen Ads Unit ID 
   at your publisher project at www.moa.com.mm
   ```java
      int showPerTime =2;
      MoaAds moaAds = new MoaAds(this);
      moaAds.initFullScreenAds(showPerTime, "fid_xxxxxxxxxxxxx");
   ```
  with the above example FullScreen will be show at every two time when user reahced
  
  # Ads Listener for MoaAdsView
  You aslo can handle Ads request success and fails with MoaAdListener  as the following
  int code is Http Status code, when error happen will return 400 and when limit ads will return 204
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
  You can aslo used MoaAdsView with the RecyclerView as the following , 
  ```java
  PeopleAdapter mPeopleAdapter = new PeopleAdapter();
    mPeopleAdapter.setItems(mList);
    MoaAdsAdapter moaAdsAdapter =
        new MoaAdsAdapter(mPeopleAdapter, this, "aid_xxxxxxxxx");
    mRecyclerView.setAdapter(moaAdsAdapter);
    ```
  adsUnitId need to replace with Ads Unit ID at your publisher project at www.moa.com.mm
  There was not support fullscreen ads type with Recyclerview adapter

  
