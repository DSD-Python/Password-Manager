# Password-Manager
A password manager created by JJ Najjar, Henry Minnick, and Jack Hurley for the DSD-Python course. The password manager is a Python application that is able to suggest a random, secure password based on the parameters given, encrypt it, and safely store that password locally for when it is needed. It aims to simplify password management for users by automating the process of creating and storing secure passwords.

Almost all people residing in a first-world country use smartphone and laptop technology as integral parts of their lives. Cybersecurity hygiene is neither well-known nor consistently practiced amongst this population. On the topic of passwords, a NordPass study revealed that the average technology user possesses over 100 online accounts that require passwords. These accounts more than likely contain personally identifiable information that can be used by bad actors to masquerade as that user and compromise the privacy of that individual. Over ⅔ of Americans use the same password for multiple accounts, leaving them incredibly vulnerable if just one password is obtained by bad actors. Others change passwords for each account but store them in obscure, non-secure places like the Notes app on iPhone or Google Documents. In both cases, people are required to create passwords meant to secure their accounts but use insecure methods to do so. Our app takes inputs from a user that describes the constraints required by an online account’s password requirements, generates a random password with the maximum allowed characters by those constraints, encrypts it using NaCl, places it into a .txt file, and stores it on the device. It is our understanding that creating a password with the maximum amount of allowed characters in a particular account instance protects against a brute force breach in that it would take more time.

An example use case would be for a user who wishes to create a nike.com account. This individual is prompted to make a password between 8-16 characters that has one capital letter and one special character. We have widgets that allow users to specify the maximum number of characters allowed, as well as the number of capital letters, numbers, and special characters required. The manager randomly selects and concatenates words from a pre-generated word list on the user's device, generating a password that meets the specific requirements. The app then encrypts the new password, and stores it locally on the device with other encrypted passwords. 

In order for the password manager to work correctly, one must perform a few simple installations, namely the following libraries:

PyQt5, nacl, and password-strength\n

This can be done by using the command "pip install ____" on a terminal window. These are dependencies that the password manager uses to create the UI, encrypt the password, and determine its strength. Moreover, one must have a form of Python installed on their device, as that is the only language the manager is written in as of now.

Users must also create a folder titled "Passwords" in their Documents, and have a file titled "passwords.lst" in that folder which is the word list from which the program randomly selects the words to use. For our implementation, we used a wordlist from https://www.openwall.com/wordlists/ that is available for purchase.

To see the password manager in action, one must download the .ipynb file from our Github repository and run it in a Python environment. We did so using Jupyter Labs.

The main elements of the project include the following:

Password Generation: Generates strong, random passwords based on user preferences (e.g., length, special characters, numbers, capital letters).

Password Encryption: Encrypts generated passwords using the NaCl library for enhanced security.

Password Decryption: Allows users to decrypt encrypted passwords by providing the secret key used for encryption.

Password Strength Evaluation: Provides an indication of the strength of generated passwords based on industry-standard metrics.

Password Saving: Offers the option to save encrypted passwords to a text file for future reference.

To use the manager, one must run the file, in which a separate window will appear and prompt the user to select the number of characters, numbers, and special characters desired in the password. It also allows the user to select if they want the password to have uppercase letters or be all lowercase. Then, the user should press "Generate Password", which will provide the user with the generated password, the encrypted password, the secret key used to encrypt the password, and the perceived "Password Strength" based on the password-strength library. Then, the manager also allows users to store that information on their device by automatically popping up another window, asking the user if they would like to do just that. If the user presses "Yes", the encrypted password and secret key will be stored in a text file in the Passwords folder on that device with a name of their choice. If the user presses "No", nothing happens. The manager also contains a button at the bottom of the original window that says "I want to decrypt", which if pressed, opens up another window that allows the user to input the encrypted password as well as the secret key used to encrypt it, and returns the original, decrypted password if given the correct inputs.

The remaining potential security concerns are largely physical, as if someone gains access to one's unlocked device, they may be able to see the Passwords folder which contains sensitive information. Encrypting that folder or the file itself may be another wise step to take that we could have looked into if we had more time. Moreover, if those files or the secret key were somehow deleted or lost, it would likely result in permanent data loss.

Additional work that remains to be done includes transporting it to other languages, and potentially encrypting the file that the encrypted password is stored in itself as previously mentioned. Also, creating an app or extension for Google Chrome that makes the program more accessible/easier to run is something that we thought would be really interesting and was yet another goal that we would have liked to pursue if we had more time.

Overall, our group was able to learn a lot from this project. Not only were we able to strengthen our coding skills and learn how to use some new libraries and tools, but it was very rewarding to create something that has an actual practical use and that we plan on using ourselves in the future.
