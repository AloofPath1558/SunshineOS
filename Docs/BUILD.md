# ☀️ SunshineOS — Build Guide

This guide explains how to build a customized **SunshineOS** ISO using **Cubic** and how to test the resulting image using **QEMU** or **VirtualBox**.

> ⚠️ **Development Notice**
>
> SunshineOS is currently under active development. Build steps may change between releases.

---

## 📋 Requirements

Before starting, make sure you have:

* A Linux system
* An **Ubuntu-based environment** recommended
* At least **20 GB of free disk space**
* An Ubuntu base ISO
* **Cubic**
* **QEMU** or **VirtualBox** for testing
* A stable internet connection

For a comfortable build environment, more than 20 GB of free space is recommended, especially when working with large ISO images.

---

# 🛠️ 1. Install Cubic

Cubic is the tool used to customize and rebuild the Ubuntu-based ISO.

On Ubuntu, install Cubic with:

```bash
sudo apt update
sudo apt install cubic
```

Alternatively, follow the official Cubic installation instructions for your distribution.

---

# 💿 2. Obtain the SunshineOS Base ISO

You can start from an existing **SunshineOS ISO** or another supported Ubuntu base ISO, depending on what you want to build.

For an existing SunshineOS release, download the ISO from the project's GitHub Releases.

The ISO is intentionally not stored directly inside the Git repository because of its large file size.

---

# 📁 3. Create a Cubic Project

Launch Cubic:

```bash
cubic
```

Create a new project and select an empty working directory.

When Cubic asks for the original ISO, select your **SunshineOS base ISO**.

Cubic will extract the ISO and prepare the filesystem for customization.

---

# 🐧 4. Customize the Filesystem

Cubic provides a terminal environment where you can modify the Linux filesystem contained inside the ISO.

For example, you can update the package lists:

```bash
apt update
```

Upgrade installed packages:

```bash
apt upgrade
```

Install additional software:

```bash
apt install <package-name>
```

Remove packages:

```bash
apt remove <package-name>
```

You can also modify configuration files, scripts, services, themes, applications, and other parts of the operating system.

> ⚠️ Be careful when removing system packages. Removing important dependencies can make the resulting ISO fail to boot or start the desktop.

---

# 🎨 5. Customize the Desktop

You can customize SunshineOS to create your own distribution or personal edition.

Possible customizations include:

* Desktop environment
* Themes
* Icons
* Wallpapers
* Fonts
* Login screen
* Applications
* System settings
* Default configuration
* Startup services
* Scripts

For example, you can install additional desktop software with:

```bash
apt install <package-name>
```

---

# ⚙️ 6. Add Your Own Configuration

You can add custom scripts and configuration files to the filesystem.

For example:

```bash
/usr/local/bin/
```

can contain custom system scripts.

Configuration files can be placed in their appropriate system locations.

Make sure that custom scripts have the correct permissions:

```bash
chmod +x /path/to/script.sh
```

---

# 📦 7. Clean Up the Build

Before generating the final ISO, it is recommended to clean unnecessary package data.

For example:

```bash
apt clean
```

You can also remove temporary files that are not required by the final system.

> 💡 The exact cleanup steps depend on the modifications made during the build.

---

# 💿 8. Generate the ISO

When customization is complete, exit the Cubic terminal and continue through the Cubic interface.

Cubic will generate the customized ISO.

Choose a suitable filename, for example:

```text
SunshineOS-Custom-1.0.iso
```

Wait for the build process to finish.

> ⏳ Building an ISO can take some time depending on your hardware, filesystem, and the amount of customization performed.

---

# 🧪 9. Test the ISO

**Always test your ISO before installing it on real hardware.**

The recommended option is QEMU.

## QEMU

Install QEMU:

```bash
sudo apt update
sudo apt install qemu-system-x86
```

Then run:

```bash
qemu-system-x86_64 \
  -enable-kvm \
  -m 4G \
  -smp 4 \
  -cpu host \
  -cdrom SunshineOS-Custom-1.0.iso \
  -boot d
```

This starts the ISO in a virtual machine.

### Check KVM

If QEMU reports that KVM is unavailable, check:

```bash
ls -l /dev/kvm
```

You can also check whether the KVM modules are loaded:

```bash
lsmod | grep kvm
```

---

# 🖥️ 10. Test with VirtualBox

VirtualBox can also be used to test the ISO.

Create a new virtual machine with:

* Type: **Linux**
* RAM: **4 GB or more**
* CPU: **2–4 cores**
* Storage: Optional virtual disk
* Optical Drive: Your SunshineOS ISO

Boot the virtual machine from the ISO and verify that:

* The system boots correctly
* The desktop starts
* Applications launch
* Networking works
* Audio works
* Custom configurations are applied
* The installer works correctly, if included

---

# 💾 11. Test on Real Hardware

After successfully testing the ISO in a virtual machine, you can test it on physical hardware.

Create a bootable USB drive using a suitable tool such as:

* Rufus
* Balena Etcher
* Ventoy
* GNOME Disks

> ⚠️ **Warning:** Writing an ISO to a USB drive can erase existing data on that drive. Double-check the selected device before writing.

Boot the target computer from the USB drive and select the SunshineOS live environment or installer.

---

# 🌱 12. Create Your Own Fork

If you want to create your own SunshineOS-based distribution:

1. Fork the SunshineOS repository
2. Clone your fork
3. Obtain the SunshineOS base ISO
4. Install Cubic
5. Create a new Cubic project
6. Import the SunshineOS ISO
7. Customize the filesystem
8. Customize the desktop
9. Add your own applications and configuration
10. Generate your ISO
11. Test the ISO with QEMU or VirtualBox
12. Publish your fork

Example:

```bash
git clone https://github.com/YOUR-USERNAME/SunshineOS.git
cd SunshineOS
```

---

# 🔄 13. Iterative Development

Building an operating system is an iterative process.

A recommended workflow is:

```text
Modify
   ↓
Build ISO
   ↓
Boot in QEMU
   ↓
Test
   ↓
Find problems
   ↓
Modify again
   ↓
Build again
```

Avoid testing experimental builds directly on your main computer whenever possible.

---

# 🐛 Troubleshooting

## ISO does not boot

Try testing the ISO with QEMU:

```bash
qemu-system-x86_64 \
  -m 4G \
  -smp 4 \
  -cdrom SunshineOS-Custom-1.0.iso
```

If the ISO works in QEMU but not on physical hardware, check the system's:

* UEFI/BIOS settings
* Secure Boot configuration
* USB creation method
* Hardware compatibility

---

## Desktop does not start

Check whether the required desktop packages and display/session components were accidentally removed.

If you removed packages during customization, try rebuilding from a clean SunshineOS base ISO.

---

## Build fails in Cubic

Check the terminal output for the first error.

Common causes include:

* Missing packages
* Broken dependencies
* Incorrect configuration files
* Insufficient disk space
* Interrupted package installation

Try:

```bash
apt update
apt --fix-broken install
```

Then rebuild the ISO.

---

# 📚 Additional Documentation

More documentation may be added as SunshineOS development continues.

Useful project resources include:

* `README.md` — Project overview
* `Docs/BUILD.md` — Build instructions
* GitHub Releases — Pre-built SunshineOS images
* `SunshineOS-Site` — Project website

---

# ☀️ Build. Experiment. Customize.

SunshineOS is designed to be experimented with.

Create your own version, change what you want, learn how the system works, and share your ideas with the community.

**Happy building! ☀️**
