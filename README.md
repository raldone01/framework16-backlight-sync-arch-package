# framework16-backlight-sync-git

An Arch Linux `PKGBUILD` for the **Framework 16 keyboard/numpad backlight sync daemon**.

🔗 **Upstream Project:** [MiguelAgueda/framework16-backlight-sync](https://github.com/MiguelAgueda/framework16-backlight-sync)

### What does it do?
On the Framework 16 laptop, the main keyboard and the Numpad/Macropad modules are handled as separate USB devices.
By default, changing the backlight brightness on the keyboard does not change it on the Numpad.
This daemon runs in the background and synchronizes the backlight levels between the modules automatically.

## Installation

You can install this package manually using `makepkg`.

### Manual Installation
Ensure you have the `base-devel` and `git` packages installed.

```bash
# Clone this repository
git clone <URL-TO-THIS-REPO>
cd <REPO-DIRECTORY>

# Build and install the package
makepkg -si
```

## Post-Installation

Once the package is installed, the daemon will not start automatically.
You need to enable and start the included `systemd` service so it runs in the background and persists across reboots.

Run the following command:
```bash
sudo systemctl enable --now fw16-backlight-sync.service
```

To check the status or view logs for the daemon, you can use:
```bash
systemctl status fw16-backlight-sync.service
```
