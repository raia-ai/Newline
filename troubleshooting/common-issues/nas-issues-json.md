---
title: "Nas Issues Json"
source: "NAS Issues JSON.pdf"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Editing BACS Date 25 September 2025 08:45 --- title: Editing BACS Date author: Newline ASP tags: [NAS, AuctionMarts, BACS, Sale Settings, M..."
long_description: "Editing BACS Date 25 September 2025 08:45"
---

Editing BACS Date
25 September 2025      08:45



---
title: Editing BACS Date
author: Newline ASP
tags: [NAS, AuctionMarts, BACS, Sale Settings, Market System]
---

# Editing BACS Date

> Summary
This guide describes how to manually edit the BACS Payment Date in the Newline Auction System
(NAS). It provides step-by-step instructions to locate the relevant configuration file, update the date,
and verify changes in the NAS interface.

## Scope & Supported Versions
- Applies to NAS version 16.0.186 and later.
- Windows-based installations with mapped drives (e.g., `Z:\`).

## Prerequisites
- Access to the NAS Sale Control system with Master rights.
- File Explorer access to the NAS sale directory (e.g., `Z:\WED`).
- Permission to edit and save text files in the sale directory.
- Basic familiarity with Notepad.

## Assumptions
- The user has sufficient privileges to update NAS configuration files.
- The Z: drive is mapped and accessible.
- The sale in question is already created in NAS.

## Procedure

1. **Open Sale Information**
  - In the NAS Sale Control window, click **About** at the top of the screen.
  - **Expected Result:** A dialog appears showing version details and the **Data Path** (sale
directory).

 #### Figure 1 — Textual Reconstruction
 _Source: About dialog screenshot_
 - **Window title:** NASBEND
 - **Version:** 16.0.186
 - **Text displayed:**
   - “Currently running options:”
   - `Data Path: Z:\WED\`
   - `Current Folder on C:\...`
   - `Master Folder: Z:\MASTER\`
 - **Buttons:** [OK]

2. **Note the Sale Directory**
  - Example: `Z:\WED\`.
  - This path will be needed in later steps.

3. **Open File Explorer**
  - Browse to the **Z:** drive.


                                         NAS Issues JSON Page 1
 - Browse to the **Z:** drive.

 #### Figure 2 — Textual Reconstruction
 _Source: Windows Explorer screenshot_
 - **Path shown:** `This PC > Z: > WED`
 - Files listed include:
   - `D.000`
   - `D.001`
   - `DATEM`
   - `DATE` (highlighted)
 - File modified dates visible.

4. **Browse to the Directory**
  - Navigate to the path recorded in Step 2 (e.g., `Z:\WED`).

5. **Locate the File**
  - Find the file named `DATE1`.

6. **Open in Notepad**
  - Right-click the file and select **Open with > Notepad**.

7. **Edit the File**
  - Locate the **bottom Date line only**.
  - Replace it with the new date in format: `DDMMYY`.
  - **Expected Result:** Only the final date line is changed.

 #### Figure 3 — Textual Reconstruction
 _Source: DATE1 file in Notepad_
 - Sample contents:
   ```
   200324
   24/03/20
   ST ASAPH WEDNESDAY
   .02B
   LIVE
   27
   N
   200324
   260324 (BACS DATE)
   Y
   N
   C
   N
   100
   N
   A
   ```
 - Bottom date line shown as `260324` (26/03/2024).

8. **Save the File**
  - In Notepad: **File > Save**.
  - Close Notepad.

9. **Verify in Market System**
  - In NAS, go to **Option 25 > Utilities Menu**.
  - **Expected Result:** Utilities Menu opens.

 #### Figure 4 — Textual Reconstruction

                                        NAS Issues JSON Page 2
 #### Figure 4 — Textual Reconstruction
 _Source: Utilities Menu screenshot_
 - **Sale Date displayed:** `20032024`
 - Menu sections:
   - **Lot Details** (options 1–7)
   - **Seller Details** (options 11–12)
   - **Buyer Details** (options 15–18)
   - **Reports / Close Sale** (options 21–23)
   - **Setup / Utilities** (options 25–30)
 - Option highlighted: `25. Utilities Menu`.

10. **Open Alter Sale Settings**
  - In the Utilities Menu, select **Option 6: Alter Sale Settings**.

  #### Figure 5 — Textual Reconstruction
  _Source: Alter Sale Settings screen_
  - **Menu title:** Utility
  - Options listed:
    - 1. Sale Merge
    - 2. Prize Menu
    - 3. Rebate System
    - 4. Alter Sale Settings
    - 20. Exit
  - Highlighted: **6. Alter Sale Settings**.

11. **Confirm the BACS Date**
  - The **Alter Sale Settings** screen now shows the corrected date.

  #### Figure 6 — Textual Reconstruction
  _Source: Alter Sale Settings window_
  - **Fields displayed:**
    - **Sale Date:** `20/03/2024`
    - **Sale Number:** `02B`
    - **Sale Description:** `ST ASAPH WEDNESDAY`
    - **Cheque Date:** `20/03/2024`
    - **BACS Payment Date:** `27/03/2024` (updated)
    - **Market Type:** [dropdown, empty]
    - **Toggles:**
      - [ ] AMS Sale
      - [ ] Buyer No Sale
      - [ ] Generic Sale (Non Livestock)
      - [ ] Lots Entered as Unsold Status
  - **Buttons:** [Save], [Exit]

## Verification
- The **BACS Payment Date** field in **Alter Sale Settings** matches the intended value.
- Reports and payment runs use the new BACS date.

## Troubleshooting
- **Issue:** Date did not update in NAS.
  - **Fix:** Ensure only the bottom date line in `DATE` was edited and saved.
- **Issue:** File is locked.
  - **Fix:** Close NAS before editing the file.
- **Issue:** Wrong format entered.
  - **Fix:** Re-edit using `DDMMYY` format.

## Rollback
- Restore the original `DATE1` file from backup.

                                        NAS Issues JSON Page 3
- Restore the original `DATE1` file from backup.
- If no backup exists, re-enter the previous date using the same procedure.

## Glossary & Key Terms
- **NAS:** Newline Auction Software
- **BACS:** Bankers’ Automated Clearing Services (UK payment clearing system)
- **Sale Directory:** Folder on Z: drive storing sale configuration files
- **DATE file:** Text file holding sale date information

## References
- Internal Newline ASP NAS Documentation v16.2
- NAS support knowledge base




                                       NAS Issues JSON Page 4
How to Change Sale Name
25 September 2025     11:09



---
title: "How to Change Sale Name"
---

# How to Change Sale Name

> Summary
This document explains how to change the name (description) of a sale in the system by navigating through the Utilities menu and modifying sale settings.

## Scope & Supported Versions
- Applies to: [Unclear from source]
- Supported environments: [Unclear from source]

## Prerequisites
- User must have access rights to **Utilities Menu**.
- An active sale must already exist in the system.

## Assumptions
- The user is logged into the system.
- The sale to be modified is already created and accessible.

## Procedure

1. **Access the Utilities Menu**
  - **Where:** **Main Menu > Option 25 (Utilities Menu)**
  - **Expected Result:** The **Setup / Utilities** screen appears, showing available options.

 #### Figure 1 — Textual Reconstruction
 - Screen title: _Setup / Utilities_
 - Options displayed:
   - 22. Sale Reports
   - 23. Close Sale
   - 25. Utilities Menu
   - 26. Setup Menu
   - 30. Exit
 - Input field: **Select Option: [ ]** (blank field where option number is entered).
 - _Source: Option 25 screenshot_

2. **Select Alter Sale Settings**
  - **Action:** Enter option **6**.
  - **Where:** **Utilities Menu > Option 6 (Alter Sale Settings)**
  - **Expected Result:** The **Alter Sale Settings** window opens.

 #### Figure 2 — Textual Reconstruction
 - Screen title: _Utility_
 - Options displayed:
   - 4. Prize Menu
   - 5. Rebate System
   - 6. Alter Sale Settings
   - 20. Exit
 - Input field: **Select Option: [ ]** (blank field where option number is entered).
 - _Source: Option 6 screenshot_

3. **Modify the Sale Description**
  - **Action:** Update the **Sale Description** field with the new sale name.
  - **Where:** **Utility > Alter Sale Settings** window.
  - **Expected Result:** The sale description is updated and saved.

 #### Figure 3 — Textual Reconstruction
 - Window title: _Alter Sale Settings_
 - Fields displayed (with example values):
   - **Sale Date:** 12/11/2024 (read-only)
   - **Sale Number:** 45G
   - **Sale Description:** HEREFROD TUESDAY (editable, highlighted for change)
   - **Cheque Date:** 12/11/2024 (read-only)
   - **BACS Payment Date:** 12/11/2024 (read-only)
   - **Market Type:** Green Market (dropdown list)
 - Checkboxes (all unchecked by default):
   - **[ ]** AMS Sale


                                        NAS Issues JSON Page 5
    - **[ ]** AMS Sale
    - **[ ]** Buyer No Sale
    - **[ ]** Generic Sale (Non Livestock)
    - **[ ]** Lots Entered as unsold status
  - Buttons at the bottom:                                  1
    - **[Save]**
    - **[Exit]**
  - Header bar displays:
    - **Sale Date:** 12/11/2024
    - **Sale Des:** HEREFROD TUESDAY
    - **Sale No:** 45G / 1256
  - _Source: Alter Sale Settings screenshot_

4. **Save the Changes**
  - **Action:** Select **[Save]**.
  - **Expected Result:** The new sale name is stored and reflected in the sale header bar.

---

## Verification
- Navigate back to the main sale screen.
- Confirm the **Sale Description** reflects the updated name.

## Troubleshooting
- If the updated name does not appear:
  - Ensure **[Save]** was selected instead of **[Exit]**.
  - Verify user has permissions to alter sale settings.
  - Restart the sale session and check again.

## Rollback
- Repeat the above procedure and re-enter the original **Sale Description**.
- Save the settings again.

## Glossary & Key Terms
- **Sale Description**: The text name assigned to a sale (e.g., "HEREFROD TUESDAY").
- **Utilities Menu**: System menu used for advanced sale configurations.
- **Alter Sale Settings**: Function allowing modifications to sale metadata.

## References
- _Source screenshots: Option 25, Option 6, Alter Sale Settings_




            1         2




                                       NAS Issues JSON Page 6
