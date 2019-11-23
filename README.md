# AppArmor profile for whole system #

Confines all, systemd, init, all systemd units, apt, all applications.

Makes pointer leaks less likely.
https://forums.whonix.org/t/kernel-hardening/7296/227

Does not confine initramfs.

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

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `apparmor-profile-everything` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`apparmor-profile-everything` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
