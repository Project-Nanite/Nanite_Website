---
title: Installation
url: "docs/installation"
weight: 4
---

# Installing Nanite Linux

Get Nanite Linux up and running on your system with our comprehensive installation guide.

## Installation Options

Nanite offers multiple installation methods to suit different needs and experience levels:

### 1. 💿 Direct Installation (Recommended)
Install Nanite directly on your hardware for the best performance and full AI capabilities.

### 2. 🖥️ Virtual Machine
Run Nanite in a VM for testing or development purposes.

### 3. 🔄 Live Boot
Try Nanite without installing it on your system.

---

## System Requirements

Before installing Nanite, ensure your system meets these requirements:

### Minimum Requirements
- **CPU**: x86_64 processor, 4+ cores
- **RAM**: 16GB (for basic AI features)
- **Storage**: 30GB free space
- **Network**: Internet connection for initial setup

### Recommended Requirements
- **CPU**: x86_64 processor, 8+ cores
- **RAM**: 32GB (for running larger AI models)
- **Storage**: 100GB+ SSD storage
- **GPU**: NVIDIA GPU with 8GB+ VRAM or AMD GPU with ROCm support
- **Network**: Broadband internet connection

### Supported Hardware
- **Graphics**: NVIDIA GTX 1060/RTX series, AMD RX 5000 series or newer
- **Storage**: NVMe SSD recommended for AI model storage
- **Network**: Wi-Fi and Ethernet supported

---

## Pre-Installation Steps

### 1. Download Nanite ISO
Get the latest Nanite Linux ISO from our official release page:
- **Stable Release**: Recommended for production use
- **Beta Release**: Latest features, may have some instability
- **Nightly Build**: Cutting-edge features, for developers

### 2. Verify Download
Always verify your ISO file integrity:
```bash
# Check SHA256 hash
sha256sum nanite-linux-x.x.x.iso

# Compare with published hash
curl -s https://releases.nanite-linux.org/checksums.txt | grep nanite-linux-x.x.x.iso
```

### 3. Create Bootable Media
Create a bootable USB drive or DVD:

**Using dd (Linux/macOS):**
```bash
sudo dd if=nanite-linux-x.x.x.iso of=/dev/sdX bs=4M status=progress
sync
```

**Using Rufus (Windows):**
1. Download and run Rufus
2. Select your USB device
3. Choose the Nanite ISO file
4. Select "Write in DD Image mode"
5. Click Start

### 4. Backup Your Data
**Important**: Always backup important data before installation.

---

## Installation Process

### Step 1: Boot from Installation Media
1. Insert your bootable USB/DVD
2. Restart your computer
3. Access boot menu (usually F12, F2, or ESC during startup)
4. Select your USB/DVD device
5. Choose "Install Nanite Linux" from the boot menu

### Step 2: Initial Setup
1. **Language Selection**: Choose your preferred language
2. **Keyboard Layout**: Select your keyboard layout
3. **Network Configuration**: Connect to Wi-Fi or Ethernet
4. **Time Zone**: Set your location and time zone

### Step 3: Disk Configuration
Choose your installation type:

**Option A: Automatic Installation**
- Nanite will automatically partition your disk
- Existing OS will be replaced
- Simplest option for dedicated Nanite systems

**Option B: Manual Partitioning**
- Create custom partitions
- Set up dual-boot configurations
- Advanced users only

**Recommended Partition Scheme:**
```
/boot/efi  - 512MB  (FAT32, for UEFI systems)
/          - 50GB   (ext4, root filesystem)
/home      - 50GB+  (ext4, user data)
/var/ai    - 100GB+ (ext4, AI models and data)
swap       - 16GB   (swap space)
```

### Step 4: User Configuration
1. **Create User Account**: Set up your primary user
2. **Set Password**: Choose a strong password
3. **Enable Auto-login**: (Optional, for convenience)
4. **AI Features**: Choose which AI features to enable by default

### Step 5: AI Model Selection
Choose which AI models to install during setup:

**Essential Models (Recommended):**
- Mistral 7B (General purpose chat)
- CodeLlama 7B (Code assistance)

**Additional Models (Optional):**
- Llama2 13B (Better quality, more resources)
- Vicuna 7B (Alternative chat model)
- Stable Diffusion (Image generation)

### Step 6: Installation
The installer will:
1. Create partitions and filesystems
2. Install base Debian system
3. Install Nanite AI components
4. Download selected AI models
5. Configure system services
6. Install bootloader

This process typically takes 20-45 minutes depending on your hardware and selected models.

---

## Post-Installation Setup

### First Boot
1. **Welcome Screen**: Complete the initial configuration wizard
2. **System Updates**: Install any available updates
3. **AI Model Verification**: Test that AI models are working correctly

### Essential First Steps

#### 1. Update System
```bash
sudo apt update && sudo apt upgrade -y
```

#### 2. Verify AI Installation
```bash
# Test AI assistant
nanite-ask "Hello, is Nanite working correctly?"

# Check available models
ollama list

# Test language model
ollama run mistral
```

#### 3. Install Additional Software
```bash
# Install additional development tools
sudo apt install build-essential git curl wget

# Install Python packages
pip install jupyter notebook matplotlib seaborn
```

#### 4. Configure GPU (if available)
```bash
# For NVIDIA GPUs
sudo apt install nvidia-driver-535 nvidia-cuda-toolkit

# For AMD GPUs
sudo apt install rocm-opencl-runtime
```

---

## Troubleshooting

### Common Installation Issues

**Issue**: Boot failure from USB
- **Solution**: Ensure USB is properly created, try different USB port, check BIOS settings

**Issue**: No internet during installation
- **Solution**: Use ethernet cable, check Wi-Fi drivers, continue without network (limited features)

**Issue**: Insufficient disk space
- **Solution**: Free up space, use external storage for AI models, choose minimal installation

**Issue**: GPU not detected
- **Solution**: Install proprietary drivers after installation, check hardware compatibility

### Getting Help

If you encounter issues during installation:

1. **Check our FAQ**: Common solutions for typical problems
2. **Community Forum**: Get help from other Nanite users
3. **GitHub Issues**: Report bugs and technical issues
4. **Documentation**: Detailed troubleshooting guides

### Post-Installation Verification

Run this checklist to ensure everything is working:

```bash
# System health check
nanite-health-check

# AI functionality test
nanite-test-ai

# Hardware compatibility check
nanite-hardware-info
```

---

## Next Steps

After successful installation:

1. **[Explore AI Features](ai-features/)** - Learn about built-in AI capabilities
2. **[Development Setup](development/)** - Configure your development environment
3. **[User Guide](user-guide/)** - Master the Nanite desktop experience
4. **[Community](community/)** - Join the Nanite community

Welcome to the future of AI-powered computing with Nanite Linux! 🚀 