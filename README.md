# fn-switch

This small and easy bash script allows to switch through Fn key modes on keyboards using <hid_apple> kernel module:

it reads and writes on <fnmode> parameter of [hid_apple] kernel module (requires sudo)

Optionally supports a basic dekstop notification with current mode through dbus call.

## Typical Installation

### Copy fn-switch in an executable path:

```
sudo cp ./fn-switch /usr/local/bin/
```

### Fix script permissions

Make sure your script file has correct ownership and permission settings. You're going to be able to run this script as root without password, so we must make sure it can be executed by everyone, but not be edited by non-root users!

```
sudo chown root:root /usr/local/bin/fn-switch
sudo chmod 755 /usr/local/bin/fn-switch
```

### Allow sudo execution for a user without password:
Enter sudoers configuration editing:
``` 
sudo visudo
```
Append the following:
```
<YOUR USERNAME> ALL=(root) NOPASSWD: /usr/local/bin/fn-switch
```

### Assign fn-switch to keyboard shortcut:
Add a keyboard shortcut for the following command:
```
fn-switch -wn
```

### Add fn-switch on startup
You can force desired fn-mode on startup with this command:
```
fn-switch -s<mode>
```

### Enjoy!