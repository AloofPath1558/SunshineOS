# ☀️ SunshineOS

Welcome to **SunshineOS**, a custom operating system project focused on experimentation, system building, and Linux-based image generation.

🌐 Live site: https://aloofpath1558.github.io/SunshineOS/

---

## 🚀 Overview

SunshineOS is a personal OS development project built to explore:

- Linux system customization
- Disk image creation and partitioning
- Boot process experimentation
- System configuration workflows
- OS deployment pipelines

This project is still under active development and is intended for educational and experimental purposes.

---

## 🧩 Project Structure


SunshineOS/
├── cubic.conf # Main configuration file
├── custom-disk/ # Disk layout / build data
├── custom-root/ # Root filesystem (excluded from GitHub if large/system files)
└── *.img / *.iso # Generated system images (not tracked in git)


---

## ⚙️ Build / Usage

Depending on your environment, SunshineOS may be built using tools like:

- Cubic (Custom Ubuntu ISO builder)
- QEMU / VirtualBox for testing
- Linux shell tools for system customization

### Example workflow:
```bash
# Build system image
# (example steps depending on your setup)

cubic build
🌐 GitHub Pages Deployment

This project includes a static website hosted via GitHub Pages:

👉 https://aloofpath1558.github.io/SunshineOS/

The site is automatically updated from the main branch.

📦 Notes
Large files like .iso and .img are not included in the repository.
System folders such as custom-root/ are excluded via .gitignore.
This repository is intended for configuration and build logic, not full OS binaries.
🧠 Goals
Build a lightweight experimental OS pipeline
Learn system internals and boot processes
Automate ISO generation workflows
Improve Linux system engineering skills
📜 License

This project is currently for personal/educational use. A license may be added in the future.

👤 Author

Created by AloofPath1558
