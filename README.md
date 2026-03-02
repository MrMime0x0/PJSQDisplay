# General Info
<br>Just know that this is a effort to create a desktop manager from Python and Javascript and then Qt languages plus i suck at coding so it will take a bit of time before i can fully start development on this project and QXD11 will be rootless except Python since that needs root for the security of the desktop manager, It also uses SELinux, AppArmor, Auditd for the main root security of Python</br>

# About
<br>What if a display server was rootless and ran on the user level instead of root, That is QXD11 and it works on allowing only the user your user to render the display or desktop and not root itself, Since we don't want root to run anything we will use JS or Javascript to render the backend stuff, And then Qt wraps around Javascript to give you a display of the desktop, While Javascript wraps around Python and this will allow Python to detect if a keylogger is running or keys are being monitored and it will detach the session while not interrupting the users workflow.</br>

# SELinux Module
<br>SELinux will act as the first layer of security basically keeping the Python module safe from bad actors if that ever comes to the MAC feature or Mandatory Access Control, And this will be a type enforcement for the python module and will have a set of rules built in so python can be safe and this needs to be run as root along side the python module.</br>

# AppArmor Module
<br>AppArmor will act as the second layer providing even more security for the JS Module and this will act as a path based profile for the rules of the JS Module hence why its the second layer to the SELinux module layer.</br>

# Auditd Module
<br>Auditd will act as the security logging module for the Python Module, JS Module, Qt Module, AppArmor Module, SELinux Module and this will log every single thing that has to do with actions that are being done on those modules and the stuff that goes on or if it goes wrong so it can be debugged by the users who use QXD11.</br>

# Python Module
<br>Python is the backend and this handles stuff like Keylogging Detection and among other modules needed for security of the Desktop Manager, This will need root but other modules like JS and Qt will not need root to function since those modules will sit in the userspace basically the main user that is using the computer.</br>

# JS Module or Javascript Module
<br>JS or Javascript will work by rendering the cursor in HTML or CSS and this will allow for the cursor to be render second after Python boots up first and JS will wrap around Python the second Python is started after the computer is started up and running</br>

# Qt Module
<br>Finally Qt, This will wrap around JS and take the rendered cursor and put it onto the desktop and this will render the rest of the desktop and this is the final process or module to be booted up and then executed, This will allow the user to see the Desktop and interact with it and Qt will not need root to function and only userspace to finally function and give the user a desktop to interact with.</br>
