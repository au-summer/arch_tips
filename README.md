## Hibernation

In order to hibernate, away from the swap partition, a resume hook is needed in `/etc/mkinitcpio.conf`.

For example:

```
HOOKS=(base udev autodetect microcode modconf kms keyboard keymap consolefont block filesystems resume fsck)
```

Then run `sudo mkinitcpio -P`


## Dolphin cannot use default applications

<https://github.com/prasanthrangan/hyprdots/issues/1406#issuecomment-2089416472>

- mkdir $HOME/.config/menus/

- curl -L https://raw.githubusercontent.com/KDE/plasma-workspace/master/menu/desktop/plasma-applications.menu -o $HOME/.config/menus/applications.menu

- kbuildsycoca6
