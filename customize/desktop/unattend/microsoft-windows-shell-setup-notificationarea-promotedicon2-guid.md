---
title: GUID
description: GUID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8aea7928-13eb-44cc-a9c8-2316097814a0
ms.prod: W10
ms.mktglfcycl: deploy
ms.sitesec: msdn
ms.author: alhopper
ms.date: 05/02/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-oem
---

# GUID


`GUID` specifies the globally unique identifier (GUID) of an icon to appear in the notification area at the far right of the taskbar.

By setting the [Path](microsoft-windows-shell-setup-notificationarea-promotedicon2-path.md) and GUID elements of the PromotedIcon2 component, you can configure another icon to appear in the notification area. This icon will appear in place of the **Battery** icon.

To select the icon to be visible, you must:

-   Select a signed binary application file that includes a notification icon.

-   Set both the **Path** and **GUID** elements for the file.

The GUID for the icon is contained in the application. The NOTIFYICONDATA shell structure contains the guidItem. For more information, see the MSDN topic: [NOTIFYICONDATA](http://go.microsoft.com/fwlink/?LinkId=120340). For third-party applications, contact your application provider to see if your application uses this structure and to obtain the GUID.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>GUID</p></td>
<td><p>Specifies the GUID of an icon to appear in the notification area.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [NotificationArea](microsoft-windows-shell-setup-notificationarea.md) | [PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md) | **GUID**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to promote a new notification icon to appear in place of the **Battery** icon.

``` syntax
  <PromotedIcon2>
    <Path>%PROGRAMFILES%\Fabrikam\Application2.exe</Path>
    <GUID>{a1bc23cb-3456-bcde-abcd-feb363cacc88}</GUID>
  </PromotedIcon2>
```

## Related topics


[PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md)

[Path](microsoft-windows-shell-setup-notificationarea-promotedicon2-path.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_unattend\p_unattend%5D:%20GUID%20%20RELEASE:%20%2810/3/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





