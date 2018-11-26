---
title: Bluetooth - BluetoothAudioProfilesVerify (Bring Up)
Description: Bluetooth - BluetoothAudioProfilesVerify (Bring Up)
ms.assetid: 
author: dawn.wood
ms.author: dawnwood
ms.date: 11/05/2018
ms.topic: article


---

# Bluetooth - BluetoothAudioProfilesVerify (Bring Up)

Verifies the current bluetooth audio device supports one of the Bluetooth Audio profiles

## Test details
|||
|---|---|
| **Specifications**  | <ul><li>Device.Audio.Bluetooth.AtleastOneProfileSupport</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows 10, client editions (ARM64)</li><li>Windows 10, mobile edition (ARM)</li><li>Windows 10, mobile edition (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 1 |
|**Category**| Development |
|**Timeout (in minutes)**| 10 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |

## More Information
### Parameters
| Parameter Name | Parameter Description |
| --- | --- |
| **WDKDeviceID** | Device id of the target Bluetooth device, if not set, tests are ran against all paired devices |


## Additional Documentation
Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s): - [Device.Audio additional documentation](device-audio-additional-documentation.md)



## Troubleshooting
For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures.](..\user\troubleshooting-windows-hlk-test-failures.md)