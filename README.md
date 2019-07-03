<p align="center">
    <a href="https://dutainformasi.net" target="_blank">
        <img src="https://s3-id-jkt-1.kilatstorage.id/cdn-dutainformasi/assets/img/logo.png" height="100px">
    </a>
    <h1 align="center">PWA to Play Store | Trusted Web Activity (TWA)</h1>
    <br>
</p>

1. Clone project ini
~~~
git clone https://github.com/virbo/Yii2ProgresiveWebApps.git
~~~

2. Edit `applicationId` di `app\build.gradle` menjadi nama package anda
~~~
...
    defaultConfig {
        applicationId "com.yiipwa.apps"
        ...
    }
...
~~~

3. Edit file `AndroidManifest.xml`, rubah `value` dan `host` menjadi alamat PWA anda
~~~
...
    <!-- Edit android:value to handle links to the target URL-->
    <meta-data
        android:name="android.support.customtabs.trusted.DEFAULT_URL"
        android:value="https://pwa.yusufayuba.net" />
    ...

    <intent-filter>
        ...
        <!-- Edit android:host to handle links to the target URL-->
        <data
            android:scheme="https"
            android:host="pwa.yusufayuba.net"/>
    </intent-filter>
...
~~~

4. Edit file `app\src\main\res\values\strings.xmls`, rubah `site` menjadi alamat PWA anda
~~~
...
    <string name="asset_statements">
        [{
            \"relation\": [\"delegate_permission/common.handle_all_urls\"],
            \"target\": {
                \"namespace\": \"web\",
                \"site\": \"https://pwa.yusufayuba.net\"}
        }]
    </string>
...
~~~

5. Create file Digital Asset Link melalui alamat https://developers.google.com/digital-asset-links/tools/generator lalu upload ke server pwa Anda. Dokumentasi lengkapnya dapat ditemukan di https://developers.google.com/digital-asset-links/v1/getting-started
