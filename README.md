# Full system AppArmor policy #

This is an AppArmor policy to confine all user space processes on the system which
allows one to enforce a strong security model and follow principle of least privilege.
An AppArmor policy for the init, systemd is loaded in the initramfs which then
applies to all other processes. Specific policies for many system services/applications
are also enforced.

This follows design ideas already present in other operating systems such as Android
and attempts to make something similar available on desktop Linux.

In addition to locking down user space, this also protects the kernel as it restricts
access to kernel interfaces like `/proc` or `/sys`, making kernel pointer and other
leaks much less likely.

This does not and cannot confine the kernel or initramfs.

This is expected to be used in combination with other security technologies such as
a hardened kernel, strong sandboxing architecture, verified boot and so on.

apparmor-profile-everything supports different boot modes: aadebug and superroot.
aadebug allows certain permissions necessary for advanced debugging and superroot
relaxes the policy substantially, even making bypasses possible. It is highly
recommended to stick to the default boot mode.

It also contains a wrapper to restrict apt as apt requires permissions that may
be abused to circumvent the policy. When updating or installing applications, you
must use the `rapt` command.

This is still in development and breakage is likely. This should only be used by
developers for now.

For now, please only use this development discussion forum thread:
https://forums.whonix.org/t/apparmor-for-complete-system-including-init-pid1-systemd-everything-full-system-mac-policy/8339

This package is produced independently of, and carries no guarantee from,
The Tor Project.
## How to install `apparmor-profile-everything` using apt-get ##

1\. Download Whonix's Signing Key.

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
