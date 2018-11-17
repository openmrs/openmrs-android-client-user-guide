# Security Features

OpenMRS ensures the security of data stored through various encryption algorithms. The database on the device is encrypted and the password properly hashed in order to secure patient data.

#### 1. Patient Identifiers are Validated


Specifically, OpenMRS uses a variation of Luhn algorithm also known as the 'mod10' algorithm. Simply put, this algorithm has the capacity to validate a variety of identification numbers. In fact, this is commonly used to validate credit card numbers. For more information, please check out the following [link](https://www.geeksforgeeks.org/luhn-algorithm/ "Luhn Algorithm") regarding the Luhn algorithm to gain a better understanding on how it works.

OpenMRS utilizes a variation of the Luhn algorithm which the Regenstrief Institue has created. In this variation, letters as well as numbers in the identifier (i.e., alphanumeric identifiers) are allowed. 

This is especially useful when creating new Patient Identifiers. Manually inputting Patient Identifiers is very prone to errors, which is why a check digit algorithm is necessary. For more information, please check out the following [link](https://wiki.openmrs.org/display/docs/Check+Digit+Algorithm "OpenMRS Luhn Algorithm Documentation") 
#### 2. Data is Transmitted Through a Secure SSL Conncection

The Secure Sockets Layer (SSL) ensures an encrypted link between the server and a browser. This ensures that the data remains private and legal. OpenMRS is verified to activate SSL on their web server. This secures the data that is being transmitted from the Android device to the web server. For more information on how SSL connection works, please visit the following [link](http://info.ssl.com/article.aspx?id=10241 "SSL Conncection").

#### 3. Strings are Hashed

Strings of data in an OpenMRS instance are encrypted at minimum using SHA-512, which is the preferred encryption method to be used by OpenMRS. SHA-512 is designed to be a one-way function. Simply put, it is very hard to decrypt an input with a brute-force search (simply trying all possible inputs). To add to this, it would take quadzillions of years to decrypt a single password. Check out the following [link](https://bitcoin.stackexchange.com/questions/41829/wont-asic-miners-eventually-break-sha-256-encryption "SHA-256") for more information.

With these security features, and more to be implemented, OpenMRS ensures that the chances of data breaches is very very remote, ensuring the privacy and security of patients and health centers using OpenMRS.
