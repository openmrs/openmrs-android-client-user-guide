# Security Features

OpenMRS ensures the security of data stored through various encryption algorithms. The whole system uses several security features which protect the data both on the client's device and on the server where patient data is stored.

### Client side

OpenMRS Android Client has a very handy feature, which is Offline Mode - it allows the user to access and modify patient data without internet connection (and synchronize it with the server database later). It's useful in places where connectivity is limited. This functionality, of course, wouldn't be possible without storing a copy of patient data on the user's smartphone.

To ensure that sensitive, personal data of the patients are safe, even if the user's device is stolen or breached, OpenMRS Android Client provides these security measures to protect the data:

##### 1. Hashing user's password

Both in online and offline mode the user has to enter their login credentials to access the system. Password verification is simple - the system compares the password from the database and user's input. The problem is that the password shouldn't be stored in the plaintext form, because it would be possible to copy it directly from device's memory - instead of storing the password itself, an [irreversible](https://learncryptography.com/hash-functions/why-are-hashes-irreversible "Why are hashes irreversible?") digest is saved. To see if the user has entered correct password, the same function is used on the user's password input and the digests are compared.

For this purpose, the OpenMRS Android app uses [BCrypt](https://en.wikipedia.org/wiki/Bcrypt "BCrypt") hashing function \(you can read more about password hashing [here](https://en.wikipedia.org/wiki/Cryptographic_hash_function#Password_verification "Password verification")\). BCrypt is currently one of the safest password hashing functions available and it is future-proof \(it's easy to increase its complexity in the future to prevent from [brute-force attacks](https://en.wikipedia.org/wiki/Brute-force_attack "Brute-force attack")\).

##### 2. Local database encryption

Managing information about patients (personal data, medical record) is a huge responsibility. To protect the copy of the data on the phone, the database is encrypted using [AES-256 cipher](https://pl.wikipedia.org/wiki/Advanced_Encryption_Standard "Advanced Encryption Standard"), which uses a combination of user's username and password as its key. This encryption function makes it impossible to decrypt the data without entering valid username and password, so even if the device is stolen or breached - it's not possible to decrypt the database without login credentials.

### Server side

##### 1. Patient Identifiers are Validated

Specifically, OpenMRS uses a variation of Luhn algorithm also known as the 'mod10' algorithm. Simply put, this algorithm has the capacity to validate a variety of identification numbers. In fact, this is commonly used to validate credit card numbers. For more information, please check out the following [link](https://www.geeksforgeeks.org/luhn-algorithm/ "Luhn Algorithm") regarding the Luhn algorithm to gain a better understanding on how it works.

OpenMRS utilizes a variation of the Luhn algorithm which the Regenstrief Institue has created. In this variation, letters as well as numbers in the identifier (i.e., alphanumeric identifiers) are allowed.

This is especially useful when creating new Patient Identifiers. Manually inputting Patient Identifiers is very prone to errors, which is why a check digit algorithm is necessary. For more information, please check out the following [link](https://wiki.openmrs.org/display/docs/Check+Digit+Algorithm "OpenMRS Luhn Algorithm Documentation")

##### 2. Data is Transmitted Through a Secure SSL Conncection

The Secure Sockets Layer (SSL) ensures an encrypted link between the server and a browser. This ensures that the data remains private and legal. OpenMRS is verified to activate SSL on their web server. This secures the data that is being transmitted from the Android device to the web server. For more information on how SSL connection works, please visit the following [link](http://info.ssl.com/article.aspx?id=10241 "SSL Conncection").

##### 3. Strings are Hashed

Strings of data in an OpenMRS instance are encrypted at minimum using SHA-512, which is the preferred encryption method to be used by OpenMRS. SHA-512 is designed to be a one-way function. Simply put, it is very hard to decrypt an input with a brute-force search (simply trying all possible inputs). To add to this, it would take quadzillions of years to decrypt a single password. Check out the following [link](https://bitcoin.stackexchange.com/questions/41829/wont-asic-miners-eventually-break-sha-256-encryption "SHA-256") for more information.

With these security features, and more to be implemented, OpenMRS ensures that the chances of data breaches is very low, ensuring the privacy and security of patients and health centers using OpenMRS.

