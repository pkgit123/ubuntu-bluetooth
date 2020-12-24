# ubuntu-bluetooth
Playbook to manage Ubuntu laptop, including bluetooth pairing

### Pair Dell XPS Ubuntu with Microsoft Surface Ergonomic Keyboard
* Tried to use the standard bluetooth GUI -> didn't work
* Trued to use CLI for `bluetoothctl` -> didn't work
* Ubuntu forum discussion about this issue.  https://ubuntuforums.org/showthread.php?t=2450326
* Install bluez.  https://core.docs.ubuntu.com/en/stacks/bluetooth/bluez/docs/install-bluez
    ```
    $ snap install bluez
    $ sudo apt install bluez
    $ snap connections bluez
    ```
* Commands for `bluetoothctl`.  https://askubuntu.com/questions/701978/how-can-a-bluetooth-keyboard-that-requires-a-code-entry-be-paired-in-the-termina
    ```
    $ bluetoothctl
    [bluetooth]# power on
    [bluetooth]# agent on
    [bluetooth]# default-agent 
    [bluetooth]# scan on
    [bluetooth]# trust [keyboard MAC Address]
    [bluetooth]# pair [keyboard MAC Address]
    Request PIN code
    [agent] Enter PIN code: 12345
    [Someone's Keyboard]# 12345
    [CHG] Device [keyboard MAC Address] Paired: yes
    ```
* Another command for `bluetoothctl`.  https://unix.stackexchange.com/questions/258074/error-when-trying-to-connect-to-bluetooth-speaker-org-bluez-error-failed
    ```
    [bluetooth]# info [keyboard MAC Address]
    ```
