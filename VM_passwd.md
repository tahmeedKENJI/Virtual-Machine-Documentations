# Linux VM Password Reset
The following steps are required if you **forget your login passwd and need to reset it**.<br>

- Start the VM but stay on alert.<br>
- When the VBox menu shows and says to **press F12** to enter boot menu, DO IT!!<br>
- From there, enter into normal boot mode by pressing "b".<br>
- Now, you will see a list of kernels. Select the appropriate kernel (usually the first one) and press "e" to enter edit mode.<br>
- find this line:<br>
```
	linux /boot/vmlinuz-5.x.x-generic root=/dev/sda1 ro quiet splash
```
    
  or something like this that starts with `linux` or `linux16`/`linuxfi` etc.<br>
- ----- **edit the "ro quiet splash" and replace with "rw init=/bin/bash"** -----<br>
- Press ``Ctrl+X`` or ``F10`` to boot with these parameters<br>
- Now you are in the root shell.<br>
- enter this command into the terminal:<br>
```
	passwd username
```
    
  where "username" is your actual username<br>
- Remount filesystem and reboot:<br>
```
	mount -o remount,ro /
   	exec /sbin/init
```
<br>

**N.B.: DO NOT STORE PASSWORDS IN PLAINTEXT FORM. DO NOT GIVE AWAY ENCRYPTION METHODS USED TO MASK YOUR PASSWORDS. ALWAYS USE STRONG PASSWORDS!**
