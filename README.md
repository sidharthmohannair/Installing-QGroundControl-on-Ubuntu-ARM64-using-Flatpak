# Installing QGroundControl on Ubuntu ARM64 using Flatpak

This tutorial will guide you through the process of installing QGroundControl (QGC) on Ubuntu ARM64 platforms using Flatpak. QGroundControl is an open-source ground control station for small unmanned vehicles that allows you to plan and execute autonomous missions.

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

## Additional Notes

- This repository provides a solution for users seeking QGroundControl support specifically tailored to ARM64 architecture.
- The provided solution has been tested and verified on Raspberry Pi 4, Raspberry Pi 3, Ubuntu 16.04, 18.04, and 20.04, as well as Nvidia Jetson Nano ARM64 series hardware.

### Issue with Pre-compiled Builds

If you encounter the error message `bash: ./QGroundControl.AppImage: cannot execute binary file: Exec format error`, it's because the pre-compiled Linux build is intended for x86-64 platforms and won’t run on ARM systems.

To address this issue:
- On ARM-based systems such as Jetson Nano, you'll need to compile QGroundControl from source to run it successfully.
- Alternatively, you can follow the tutorial provided in this repository for step-by-step instructions on installing QGroundControl on ARM64 platforms using Flatpak.

