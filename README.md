# -TagUI-RPA-Challenge---Week-4
#### https://community.aisingapore.org/groups/tagui-rpa/forum/discussion/rpa-challenge-submissions/page/2/
##### https://developer.automationanywhere.com/blog/challenge-page-introaccountspayablechallenge

#
Here is my approach:
1) Create empty dataframe with fixed columns (['FileName','InvoiceNumber','InvoiceDate','InvoiceTotal','Quantity','Desciption','Price'])

2) Iterate thru each invoice file (pre-downloaded in a folder)<br/>
  2.1) Identify the type of invoice format based on keywords<br/>
  2.2) Convert invoice image into text using PyTesseract<br/>
  2.3) Extract required data from text using various Python string methods<br/>
  2.4) Append required data into dataframe

3) Access 'Invoice Processing' webpage. Ensure chrome browser open in foreground using click('chrome.png') onto the taskbar.

4) Iterate thru unique 'FileName' from dataframe<br/>
  4.1) Input 'InvoiceNumber', 'InvoiceDate', 'InvoiceTotal'<br/>
  4.2) Iterate thru each line item<br/>
     4.2.1) If second line item, click 'Add Item' button<br/>
     4.2.2) Input 'Quantity', 'Desciption', 'Price'<br/>
  4.3) Click 'Choose File' button<br/>
  4.4) Save full path (to invoice image) to clipboard<br/>
  4.5) Perform keystrokes to input full path or filename into 'Upload' window.<br/>
  4.6) Click 'Yes' radio button<br/>
  4.7) Click 'Submit' button<br/>


Note 1: In Step 4.5 for uploading invoice image for the first time during the run, robot will use keystrokes to copy and paste the full path (to the image) into 'Upload' window, and for second invoice image and onward, robot will use keystrokes to type the filename (of the image) into 'Upload' window.

Note 2: User need to avoid moving the mouse cursor and typing of keyboard during robot run.
