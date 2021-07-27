# How to verify a checksum on Apple Mac

## Overview

This page shows how to make sure that the installer has not been corrupted during the download process. 

## Get the hash from the website

The image shows the wallet page; the same principles apply to the client page.
![Windows installer](../images/9-wallet-checksum.png)

The SHA-256 value is below the installer. Copy and paste it to a spreadsheet or your favorite comparison tool.


## Get the hash from the downloaded file

To calculate the checksum of the downloaded file, open a shell terminal and go to the folder containing the file.
Enter the following command:  
`shasum -a 256 <file name>`  
Mac OSX will display the hash value in the terminal window.

Copy and paste the calculated value.

## Compare the values

If they are equal, you are good to go.

If not, try downloading again.
