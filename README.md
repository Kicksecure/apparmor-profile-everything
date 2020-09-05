# AppArmor profile for whole system #

Confines all, systemd, init, all systemd units, apt, all applications.

Makes pointer leaks less likely.

Does not confine initramfs.

Still in development.

Developers only!

For now, please only use this development discussion forum thread:
https://forums.whonix.org/t/apparmor-for-complete-system-including-init-pid1-systemd-everything-full-system-mac-policy/8339

This package is produced independently of, and carries no guarantee from,
The Tor Project.
## How to install `apparmor-profile-everything` using apt-get ##

1\. Download [Whonix's Signing Key]().

```
wget https://www.whonix.org/patrick.asc
```

Users can [check Whonix Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key) for better security.

2\. Add Whonix's signing key.

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg add ~/patrick.asc
```

3\. Add Whonix's APT repository.

```
echo "deb https://deb.whonix.org buster main contrib non-free" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `apparmor-profile-everything`.

```
sudo apt-get install apparmor-profile-everything
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions. (Replace `generic-package` with the actual name of this package `apparmor-profile-everything`.)

* **A)** [easy](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`apparmor-profile-everything` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
