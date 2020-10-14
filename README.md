<h1 align="center">Live RSS Feed Reader</h1> 

<p align="center">
An Android application made in Android Studio and coded with Java, that converts live RSS feed XML data into organized read-able sections for an end user. The concept of this app is that every mainstream company or website has a live RSS feed in which data is updated continously in XML. So, I made a live RSS feed reader that uses this live XML data and converts it into read-able sections for a user to toggle between pages and have a better user experience. This app has three sections, top free apps, paid apps, and songs. Each page has the name of the app, the company which created it, and the given summary of each of their purposes and uses. Users can also toggle between top 10 and top 25. 
</p>

<p align="center">
A link to an APK file for Android users can be found here: <a href="https://github.com/aahmad4/Live-RSS-Feed-Reader/blob/master/app-debug.apk" target="_blank">app-debug.apk</a>
</p>

## App Platform
 
 ![](screenshot1.png) ![](screenshot2.png)

## Data Source

 For showcase, I used Apples top chart section for free apps, paid apps, and songs. However, this can be done with any live RSS feed.
 Apples RSS information can be found  [here](https://www.apple.com/rss/).
  
## Setup
#### Clone
 
 ```
 git clone https://github.com/aahmad4/Live-RSS-Feed-Reader
 ```
 
#### Implementation
 
 In [MainActivity.java](https://github.com/aahmad4/Live-RSS-Feed-Reader/blob/master/app/src/main/java/com/example/top10downloader/MainActivity.java) change `feedUrl` to the RSS feed you want to use.
 ```java
 public class MainActivity extends AppCompatActivity {
    private static final String TAG = "MainActivity";
    private ListView listApps;
    private String feedUrl = "http://ax.itunes.apple.com/WebObjects/MZStoreServices.woa/ws/RSS/topfreeapplications/limit=%d/xml";
    private int feedLimit = 10;
    private String feedCachedUrl = "INVALIDATED";
    public static final String STATE_URL = "feedUrl";
    public static final String STATE_LIMIT = "feedLimit";
```

Likewise, in [MainActivity.java](https://github.com/aahmad4/Live-RSS-Feed-Reader/blob/master/app/src/main/java/com/example/top10downloader/MainActivity.java) change `feedUrl` to the different RSS feeds you would like to view.
```java
switch(id) {
  case R.id.mnuFree:
      feedUrl = "http://ax.itunes.apple.com/WebObjects/MZStoreServices.woa/ws/RSS/topfreeapplications/limit=%d/xml";
      break;
  case R.id.mnuPaid:
      feedUrl = "http://ax.itunes.apple.com/WebObjects/MZStoreServices.woa/ws/RSS/toppaidapplications/limit=%d/xml";
      break;
  case R.id.mnuSongs:
      feedUrl = "http://ax.itunes.apple.com/WebObjects/MZStoreServices.woa/ws/RSS/topsongs/limit=%d/xml";
      break;
```

#### Usage
 
Initiate a debug APK build:
```
gradlew assembleDebug
```
Build APK and immediately install on running emulator or connected device:
```
gradlew installDebug
```
Mac or Linux Prefix:
```
./gradlew task-name
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
 
