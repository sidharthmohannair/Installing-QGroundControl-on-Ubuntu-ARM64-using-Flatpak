# Installing QGroundControl on Ubuntu ARM64 using Flatpak

This tutorial will guide you through the process of installing QGroundControl (QGC) on Ubuntu ARM64 using Flatpak. QGroundControl is an open-source ground control station for small unmanned vehicles that allows you to plan and execute autonomous missions.

## Prerequisites
* Ubuntu ARM64 system (e.g., Raspberry Pi 4, Jetson Nano).
* Internet connection.
* Basic familiarity with the terminal.

## Step 1: Install Flatpak 1.12.4

1. Open a terminal on your Ubuntu ARM64 system.
2. Run the following commands to install Flatpak 1.12.4:

```bash
sudo add-apt-repository ppa:alexlarsson/flatpak
sudo apt update
sudo apt install flatpak
```

## Step 2: Add Flathub and thopiekar.eu Repositories
1. Add the Flathub repository:

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
2. Add the thopiekar.eu repository:
```bash
flatpak remote-add --if-not-exists thopiekar.eu https://dl.thopiekar.eu/flatpak/_.flatpakrepo
```
## Step 3: Install QGroundControl
1. Install the KDE runtime:
```bash
flatpak install flathub org.kde.Platform/aarch64/5.15-21.08
```
2. Install QGroundControl:
```bash
flatpak install thopiekar.eu org.mavlink.qgroundcontrol
```

## Step 4: Run QGroundControl
After installation, you can run QGroundControl using the following command:

```bash
flatpak run --device=all org.mavlink.qgroundcontrol
```
The `--device=all` option is required for accessing devices like serial ports.

**Congratulations! You have successfully installed QGroundControl on your Ubuntu ARM64 system using Flatpak. You can now use QGroundControl to plan and execute missions for your unmanned vehicles.**

## Notes
If you encounter any issues during installation, make sure your system meets the prerequisites and that you have a stable internet connection.
QGroundControl may require access to various devices on your system, such as serial ports. Ensure that you grant necessary permissions when prompted.
