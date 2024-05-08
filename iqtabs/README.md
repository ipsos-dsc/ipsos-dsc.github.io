# iQTabs

iQTabs helps you with creating : 

## Setup.mrs File

### **INPUT**

**`1. Table Specifications File ( in .xlsx format )`**

- iQTabs supports 3 Tab - Spec formats, namely ***A***, ***B*** and ***Auto Tab Plan***. Check out some examples [***here***](https://ipsosgroup-my.sharepoint.com/:x:/g/personal/piyush_patre_ipsos_com/Ea22EKRbODJMsLNpoYkDKwoBv3D2RXhoJrRbgRZeA-_Nvw?e=HTFId4).

- Make sure that your Tab - Spec file is inline with any one of the sheets in the link above

**`2. MDD File`**
- Just your regular mdd file

### **OUTPUT**

**`1. Setup.mrs file`**
-  This file contains the tabulation script that does the heavy lifting for you.

**`2. Summary Report`**
- This Excel file shows you any manual tweaks you might need to make in the setup.mrs file

**`3. log file`**
- You could receive warning messages like : 

    ***Pleaae update the question variable [variable name] at [row number] as per mdd***

    The above warning message refers to the row number of column A of the the Tab-Specs sheet that has the name of the variable mantioned incorrectly, according to the mdd file.


***Heads up:***
---
***To use iQTabs efficiently, update the variables according to the mdd, re-upload it and run it again***