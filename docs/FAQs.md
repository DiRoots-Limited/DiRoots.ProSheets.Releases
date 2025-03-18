---
layout: default
title: FAQs
nav_order: 99
---

# Frequently Asked Questions about ProSheets

This section aims to answer the our users' frequently asked questions.

## Does ProSheets requires PDF24?

Yes. The correct version of PDF24 will be automatically installed alongside ProSheets.

```
Uninstalling PDF24 will lead ProSheets to stop working.
```

## Can I select another PDF printer?

No. ProSheets works only with PDF24.

## What is the printer called diroots.prosheets that I got after installing ProSheets?

diroots.prosheets printer is a custom instance of PDF24 that ProSheets uses to set up its custom settings without affecting the main instance of PDF24.

## Why I can't see the PDFs being created in the output location?

If you don't see the PDF files appearing in the export path, it means that there are some issues with your settings. You can fix it, using one of the methods below.

**Method A**  

Open PDF24 -> Settings -> Printer Driver and confirm that your settings are as per the image below.

![ProSheets Selecting Revit Sheets and Views](../assets\images\PS-Print-Settings.png)  

**Method B**  

1. uninstall ProSheets and PDF24
2. download and install the [latest version of ProSheets](https://diroots.com/revit-plugins/revit-to-pdf-dwg-dgn-dwf-nwc-ifc-and-images-with-prosheets/) from our website.
3. restart your computer and try again 

## Why I ProSheets tells me that my printer is in an error state?

If ProSheets is telling you that your printer is in error state, it means that the Windows printer services stopped working.  
Often, restart your computer is enough to fix the problem.

## Printer Permission Issue in ProSheets

### Problem
If you receive an error stating: `Unable to select Printer Printer Name` or `Failed to access print parameters`, this typically points to a printer driver or permissions issue that prevents ProSheets from accessing complete printer information. Alternatively, it may indicate that no default printer is set on the system.

The Revit Print API works by first querying the available printers on the machine and then configuring the selected printer based on the format settings. Unfortunately, if any printer driver on the system is problematic, the Revit Print API may enter an error state. Even if the problematic printer is not actively in use, this error can still occur. Restarting Revit is often required to reset the error.

### Solution
**1. Identify the Default Printer**  
First, confirm that your system has a Default Printer. In Windows 10/11, there is an option called "Allow Windows to manage my default printer." If this option is enabled, your system automatically sets a default printer. If this is disabled, manually assign a default printer from the list of available devices.  

If the default printer is correctly set and the issue persists, proceed to identify the problematic printer driver by systematically disabling printers until the error clears.  

**2. Verify Printer Permissions**  
The user must have administrative permissions for the PDF24 Printer.  
To enable permissions:  
- Go to **Devices and Printers**.  
- Right-click on **PDF24 Printer** and select **Printer Properties**.  
- Navigate to the **Security** tab.  
- Ensure the following options are enabled for your user:  
   - **Manage this printer**  
   - **Manage documents**  

**3. Additional Considerations**  
If your printers are created via a login script or group policy, the problematic printer may reappear with each login. If this occurs, contact your **System Administrator** for further assistance in identifying and resolving the problematic printer driver.  

Several users have reported that the root cause of this issue was linked to a **network printer**. Identifying and disabling this printer often resolved the error.

By following these steps, you should be able to resolve printer-related issues when using **DiRoots ProSheets** and **PDF24**.