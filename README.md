# cordova-plugin-open-overlay-permission
This plugin is for checking and opening overlay permission for android devices.
The idea for this plugin came from a problem with full screen intent notifications in new android versions that require
the user to explicitly give permission for app to overlay the screen

# Installation
`cordova plugin add cordova-plugin-open-overlay-permission`

# Supported Platforms
* Android

# Methods
## openOverlayPermission
Open the settings for current app
```
(<any>window).plugins.OpenOverlayPermissionPlugin.openOverlayPermission([], (success) => {
            successCallback(success);
        }, (error) => {
            errorCallback(error);
});
```
## canDrawOverlays
Checks if the app can draw on top of other apps
```
(<any>window).plugins.OpenOverlayPermissionPlugin.canDrawOverlays([], (success) => {
            successCallback(success);
        }, (error) => {
            errorCallback(error);
        });
```
## isMIUI
Return if the current device OS is Xiaomi's MIUI
```
(<any>window).plugins.OpenOverlayPermissionPlugin.isMIUI([], (ismiui) => {
                if (ismiui === "true") {
                    this.isMIUI = true;
                }
            }, (error) => {
                this.isMIUI = false;
});
```

## Quirks
In xiaomi's MIUI, the user will have to give:
*Display pop-up windows while running in the background* permission in **other permissions** section of the app settings.
**openOverlayPermission** method will open the right settings window depend on the device OS
