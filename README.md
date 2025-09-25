## Hibernation

In order to hibernate, away from the swap partition, a resume hook is needed in `/etc/mkinitcpio.conf`.

For example:

```
HOOKS=(base udev autodetect microcode modconf kms keyboard keymap consolefont block filesystems resume fsck)
```

Then run `sudo mkinitcpio -P`

### Hibernate without compression

With swap partition as large as RAM, hibernation can be done without compression.

Add `hibernate=nocompress` to the kernel parameters in /etc/default/grub.

Then run `sudo grub-mkconfig -o /boot/grub/grub.cfg`.

## Dolphin cannot use default applications

<https://github.com/prasanthrangan/hyprdots/issues/1406#issuecomment-2089416472>

- mkdir $HOME/.config/menus/

- curl -L https://raw.githubusercontent.com/KDE/plasma-workspace/master/menu/desktop/plasma-applications.menu -o $HOME/.config/menus/applications.menu

- kbuildsycoca6

## Sudo with no timeout

Add `Defaults timestamp_timeout=0` to `/etc/sudoers`
