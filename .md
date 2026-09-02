# Contributing to ![Logo](https://raw.githubusercontent.com/AloofPath1558/SunshineOS/refs/heads/main/Assets/Logo.png)

Thank you for your interest in contributing to **SunshineOS**! ☀️

SunshineOS is an experimental Linux distribution project focused on system customization, Linux development, and learning.

Contributions, ideas, improvements, and feedback are welcome.

---

## 🤝 How to Contribute

There are several ways you can contribute to SunshineOS:

* 🐛 Report bugs
* 💡 Suggest new features
* 📝 Improve documentation
* 🎨 Improve the desktop experience
* 🛠️ Improve build scripts
* 🧪 Test new releases
* 🔧 Submit code or configuration changes
* 🌱 Create and share your own SunshineOS fork

---

## 🍴 Creating a Fork

To create your own version of SunshineOS:

1. Fork the repository on GitHub
2. Clone your fork
3. Create a new branch
4. Make your changes
5. Build and test your modified ISO
6. Commit your changes
7. Push your branch
8. Open a Pull Request

---

# 📥 Repository Setup

After creating your fork, clone it to your local machine.

```bash
git clone https://github.com/YOUR-USERNAME/SunshineOS.git
cd SunshineOS
```

Add the original SunshineOS repository as an `upstream` remote:

```bash
git remote add upstream https://github.com/AloofPath1558/SunshineOS.git
```

You can verify your remotes with:

```bash
git remote -v
```

You should see something similar to:

```text
origin    https://github.com/YOUR-USERNAME/SunshineOS.git
upstream  https://github.com/AloofPath1558/SunshineOS.git
```

---

## 🌿 Create a Branch

Create a separate branch for your changes instead of working directly on `main`.

```bash
git checkout -b my-changes
```

For example:

```bash
git checkout -b improve-documentation
```

---

# 🛠️ Build Setup

SunshineOS is built using an Ubuntu-based workflow and **Cubic**.

Before building, make sure your system has the required tools.

On Ubuntu:

```bash
sudo apt update
sudo apt install cubic qemu-system-x86
```

You may also install VirtualBox if you want to use it for testing.

---

## 💿 Obtain a Base ISO

Download or obtain a **SunshineOS base ISO**.

The base ISO can be obtained from the project's GitHub Releases.

Large ISO files are not stored directly in the Git repository.

---

## 🔧 Build SunshineOS

For detailed build instructions, see:

**[`Docs/BUILD.md`](Docs/BUILD.md)**

The general workflow is:

1. Start **Cubic**
2. Create a new Cubic project
3. Select the SunshineOS base ISO
4. Customize the filesystem
5. Customize the desktop and system configuration
6. Generate the new ISO
7. Test the ISO

---

## 🧪 Testing Changes

Before submitting a Pull Request, test your changes whenever possible.

The recommended testing method is **QEMU**.

Example:

```bash
qemu-system-x86_64 \
  -enable-kvm \
  -m 4G \
  -smp 4 \
  -cpu host \
  -cdrom SunshineOS-Custom.iso \
  -boot d
```

You can also use **VirtualBox**.

Check that:

* The ISO boots correctly
* The desktop starts
* Networking works
* Applications launch
* Your changes are applied
* The installer works, if applicable

---

# 💾 Commit Your Changes

After making and testing your changes:

```bash
git status
```

Add the files you changed:

```bash
git add .
```

Create a commit:

```bash
git commit -m "Describe your changes"
```

For example:

```bash
git commit -m "Improve desktop configuration"
```

---

# 🚀 Push Your Branch

Push your branch to your fork:

```bash
git push -u origin my-changes
```

Then open your fork on GitHub and create a **Pull Request** to the main SunshineOS repository.

---

# 🔄 Keeping Your Fork Updated

You can update your local copy from the original SunshineOS repository with:

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

Then push the updated `main` branch to your fork:

```bash
git push origin main
```

---

# 📥 Pull Requests

When opening a Pull Request, please provide:

* A clear title
* A description of what was changed
* Why the change was made
* Information about testing
* Any known issues

Example:

```text
Title:
Improve default desktop configuration

Description:
Updated the default desktop configuration and improved
the initial user experience.

Testing:
Tested successfully in QEMU.
```

---

# 🐛 Reporting Bugs

When reporting a bug, please include as much useful information as possible.

For example:

* SunshineOS version
* Hardware
* CPU / GPU
* RAM
* What happened
* What you expected to happen
* Steps to reproduce the problem
* Relevant error messages or logs

Screenshots are also welcome when they help explain the problem.

---

# 💡 Feature Requests

Have an idea for SunshineOS?

Feel free to suggest it.

A useful feature request should explain:

1. What the feature does
2. Why it would be useful
3. How you think it could work
4. Any possible drawbacks

Not every suggestion will necessarily be implemented, but feedback helps guide development.

---

# 📚 Documentation

Documentation improvements are always welcome.

You can improve:

* `README.md`
* `ROADMAP.md`
* `CONTRIBUTING.md`
* `Docs/BUILD.md`
* Other documentation inside the `Docs/` directory

Please keep documentation clear and easy to understand.

---

# 🌱 SunshineOS Forks

SunshineOS encourages experimentation.

You are welcome to create your own SunshineOS-based distribution and customize it for your own needs.

You can change things such as:

* Desktop environment
* Themes
* Applications
* System configuration
* Wallpapers
* Scripts
* Default software
* Other system components

Have fun experimenting! ☀️

---

# 📜 Code and Project Guidelines

When contributing, try to:

* Keep changes focused
* Keep documentation up to date
* Avoid unnecessary changes
* Test changes before submitting them
* Explain significant changes
* Keep the project easy to understand

---

# ❤️ Community

Please be respectful and constructive when interacting with other SunshineOS contributors and users.

Different ideas and approaches are welcome.

The goal is to build, experiment, learn, and improve together.

---

# ☀️ Thank You!

Every contribution helps SunshineOS grow.

Whether you report a bug, improve the documentation, test an ISO, suggest an idea, or contribute code — **thank you for helping the project!**

**Build. Experiment. Customize.**

☀️ **SunshineOS**
