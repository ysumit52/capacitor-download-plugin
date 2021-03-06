# Capacitor-Download-Plugin
Download and Install apk using direct link on the server

OR

Download any file from the server by making changes defined below for files like pdf, jpg , mp4 and more

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/)


## Installation

`npm i https://github.com/ysumit52/capacitor-download-plugin`

Minimum Capacitor version is **1.0.0**

## Configuration

This example shows the common process of configuring this plugin.

### Use it

```typescript
import {
  Plugins
} from '@capacitor/core';

@Component({
  template: '<button (click)="clickDownload()">Download Any file</button>'
})
export class LoginComponent {
   
     clickDownload(appUrl){
        const details = {
          url : appUrl,
          folderName : 'folderName',
          contentType: 'application/vnd.android.package-archive',
          fileName :  'randomName.apk',
          downloadAndInstall :  true
        };
        const pluginValue = Plugins.DownloadPlugin.download(details).then(() => {
            // do stuff
        }).catch(error => {
            console.error("File downlaodin failed", error.message);
        });
      }
}
```
# Use of contentType
If pdf : "application/pdf"

If apk : "'application/vnd.android.package-archive'

else check other file details

**Id black pass the file extension in fileName eg. randomFile.pdf**

# Use of downlaodAndInstall Object parameter in JSON

If **downloadAndInstall** = true (It will ask a pop up to install the apk(only apk) directly)

Else only want to download the file then pass **downloadAndInstall** = false 

## Platform: Web/PWA

No further config is needed.

## Platform: Android

**Register the plugin** in `com.companyname.appname.MainActivity#onCreate`

```
import com.knight.plugin.download.DownloadPlugin;


    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        List<Class<? extends Plugin>> additionalPlugins = new ArrayList<>();
        // Additional plugins you've installed go here
        // Ex: additionalPlugins.add(TotallyAwesomePlugin.class);
        additionalPlugins.add(DownloadPlugin.class);

        // Initializes the Bridge
        this.init(savedInstanceState, additionalPlugins);
    }
```

## Platform: iOS

- No timeline.

## Platform: Electron

- No timeline.

## Contribute


## Changelog


## License

MIT. 

## KnightCrawler Software & Consulting

This plugin is powered by **KnightCrawler**

