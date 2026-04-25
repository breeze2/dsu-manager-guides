# DSU Manager Guides

[![GitHub Release](https://img.shields.io/github/v/release/breeze2/dsu-manager-guides)]()
[![Github All Releases](https://img.shields.io/github/downloads/breeze2/dsu-manager-guides/total.svg)]()

See [DSU Controller](https://github.com/breeze2/dsu-controller-guides#run-with-dsu-manager-on-windows)

🚧 Under Construction 🚧

## For Linux

### Install

```bash
sudo dpkg -i dsu-manager_0.6.0_amd64.deb
```

### Grant Permissions

```bash 
sudo modprobe uinput
echo 'KERNEL=="uinput", MODE="0660", GROUP="input"' | sudo tee /etc/udev/rules.d/99-uinput.rules > /dev/null
sudo usermod -aG input "$USER"
sudo udevadm control --reload-rules
sudo udevadm trigger
```

Notes:
- loads the uinput kernel module (required for virtual input devices).
- writes a udev rule so users in the input group can access /dev/uinput.
- adds your current user to the input group.
- reloads and applies udev rules immediately.
- You usually need to REBOOT for new group membership to take effect.

