# ACME Vendor Invoice Automation

This repository contains an RPA project designed to automate the processing and calculation of vendor invoices using UiPath. The project interacts with the ACME System1 web application, processes data from an Excel file, and sends the output via email.

## Features
- Logs into the ACME System1 platform.
- Extracts vendor data from the `VendorInvoicesData.xlsx` file.
- Downloads monthly invoices for each vendor from the ACME platform.
- Calculates total invoices for each vendor and updates the Excel file.
- Saves the updated file and uploads it to OneDrive using a custom API integration.
- Sends the output file via email.

## Process Overview
1. **Launch ACME System1**
   - Navigate to [ACME System1](https://acme-test.uipath.com).
   - Log in 

2. **Input File Preparation**
   - Use the file `VendorInvoicesData.xlsx`.
   - Add a new column named `Total Invoices` to the `Vendors` sheet.

3. **Extract Vendor Data**
   - Extract vendor information from the `Vendors` sheet and upload the data to the robot queue.

4. **Process Each Vendor**
   - Navigate to the "Internal Invoices" tab for each vendor.
   - Download monthly invoices from January to December using the Vendor Value.
   - Populate the downloaded data into the `Vendor Invoices` sheet.

5. **Calculate Total Invoices**
   - Use the populated `Vendor Invoices` sheet to calculate the total invoices for each vendor.
   - Update the `Total Invoices` column in the `Vendors` sheet.

6. **Save and Upload the Output File**
   - Save the updated Excel file locally.
   - Upload the file to OneDrive using a custom API integration (without UiPath's OneDrive library).

7. **Send Output File via Email**
   - Email the updated file to the intended recipient(s).

## Requirements
- UiPath Studio (Classic Activities enabled).
- Input File: `VendorInvoicesData.xlsx`.
- Access to the ACME System1 platform.
- OneDrive API credentials for custom integration.

## Setup and Execution
1. Clone the repository.
2. Open the UiPath project in UiPath Studio.
3. Place the `VendorInvoicesData.xlsx` file in the designated input folder.
4. Configure OneDrive API credentials in the project settings.
5. Run the automation.
6. Verify the output file in OneDrive and email inbox.

## Output
- An updated `VendorInvoicesData.xlsx` file with:
  - Total monthly invoices downloaded for each vendor.
  - Calculated `Total Invoices` values added to the `Vendors` sheet.

## Contact
For any issues or queries, feel free to raise an issue in the repository.

---

This project demonstrates efficient automation of repetitive tasks using UiPath, custom API integrations, and data processing techniques.
