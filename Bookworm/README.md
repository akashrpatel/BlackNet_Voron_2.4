mainsailos -> bookworm confersion

```
sudo sed -i 's/bullseye/bookworm/g' /etc/apt/sources.list
sudo sed -i 's/bullseye/bookworm/g' /etc/apt/sources.list.d/raspi.list
```

some GPG keys will need to be upgrade. i.e. tailscale

first we have to update the repo and upgrade the base.
```
sudo apt update && sudo apt upgrade -y 
```

followed by these

```
sudo apt full-upgrade -y 
sudo apt autoremove -y
```

some packages will want confirmation to update config files,  one option is just say Y on all.  you can do D to display the differences.

```
Configuration file 'xxxxxxxxxxx'
 ==> Modified (by you or by a script) since installation.
 ==> Package distributor has shipped an updated version.
   What would you like to do about it ?  Your options are:
    Y or I  : install the package maintainer's version
    N or O  : keep your currently-installed version
      D     : show the differences between the versions
      Z     : start a shell to examine the situation
 The default action is to keep your current version.
*** rsyslog (Y/I/N/O/D/Z) [default=N] ?
```


fails with libmpv-dev
    ```
sudo apt install libmpv-dev
reboot
```

reinstall klipper
reinstall moonraker

notes for bookworm changes to date.
* python is now forced to be in virtual environments

