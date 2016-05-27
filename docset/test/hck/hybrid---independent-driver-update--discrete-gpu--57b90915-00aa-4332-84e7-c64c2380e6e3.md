---
author: joshbax-msft
title: Hybrid - Independent Driver Update (Discrete GPU)
description: Hybrid - Independent Driver Update (Discrete GPU)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7a748149-d3d4-4083-b9bb-930079aa908b
---

# Hybrid - Independent Driver Update (Discrete GPU)


The test uses the Microsoft Basic Render device as dGPU paired with IHV iGPU. A basic Hybrid Present test is run on this configuration to validate that it is still a valid Hybrid configuration and that Hybrid functionality is preserved.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>System.Fundamentals.Graphics.HybridGraphics.MultiGPU</p>
<p>[See the system hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254482)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows RT 8.1 Windows 8.1 x64 Windows 8.1 x86 Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~30 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [WDTF System Fundamentals Testing Prerequisites](wdtf-system-fundamentals-testing-prerequisites.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting System Fundamentals Testing](troubleshooting-system-fundamentals-testing.md).

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Error</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conformance issues</p></td>
<td><p>When the test detects a conformance issue, it saves an image in the test directory if the <strong>-saveBMP</strong> parameter is specified. You can view this image to help diagnose the issue.</p></td>
</tr>
<tr class="even">
<td><p>Cross Adapter Present validation failures</p></td>
<td><p>To get more information about the failure, run the test under User Mode Debugger. The test will output the information that it gets from ETW events, to help diagnose the failure.</p></td>
</tr>
</tbody>
</table>

 

## More information


### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>-saveBMP</strong></p></td>
<td><p>By using this parameter, the test saves presented images in BMP format to the test directory in case of conformance failure. This is useful for diagnosing conformance failures.</p></td>
</tr>
<tr class="even">
<td><p><strong>-whql | -featurelevel:&lt;fl&gt;</strong></p></td>
<td><p><strong>-whql</strong> results in device creation with highest support on a given adapter. <strong>–featurelevel:&lt;fl&gt;</strong> creates a device of requested feature level</p>
<p>Default value: <strong>-wqhl</strong> for DX10+ drivers; <strong>-featurelevel</strong>:9.1 for DX9 drivers</p></td>
</tr>
<tr class="odd">
<td><p><strong>-hybrid</strong></p></td>
<td><p>This value forces application execution on dGPU as if it was on the DList.</p></td>
</tr>
</tbody>
</table>

 

 

 





