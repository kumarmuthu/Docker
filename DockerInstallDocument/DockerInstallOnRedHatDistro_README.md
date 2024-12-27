# Docker Installation and Setup Guide for Red Hat Distro

This guide explains the steps to install Docker, manage the Docker service, and troubleshoot installation issues.

## Step 1: Install `dnf` and `yum-utils`

To enable additional repository management functionality and ensure smooth installation, first install `dnf` (a more advanced version of `yum`) and `yum-utils.

### Install dnf
```bash
sudo yum install dnf
```

### Install yum-utils for managing repositories
```bash
sudo yum install -y yum-utils
```

## Step 2: Add Docker's Official Repository

Next, add Docker’s official repository to your system. This will ensure you get the latest Docker packages.

### Add Docker's official repository for CentOS
```bash
sudo yum-config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
```

## Step 3: Install Docker and Related Tools

Now that the repository is added, install Docker and its related packages:

### Install Docker, Docker CLI, and containerd.io
```bash
sudo yum install -y docker-ce docker-ce-cli containerd.io
```

## Step 4: Start Docker Service

Once Docker is installed, start the Docker service to begin using Docker containers:

### Start Docker service
```bash
sudo systemctl start docker
```

## Step 5: Enable Docker to Start on Boot

To ensure Docker starts automatically when the system reboots, enable it to start at boot:

### Enable Docker service to start on boot
```bash
sudo systemctl enable docker
```

## Step 6: Troubleshooting: Reinstall Docker (if necessary)

If Docker is not working as expected, you can remove and reinstall Docker using the following commands:

### Remove Docker and related packages
```bash
sudo yum remove -y docker-ce docker-ce-cli containerd.io
```

### Reinstall Docker and related packages
```bash
sudo yum install -y docker-ce docker-ce-cli containerd.io
```

## Step 7: Check Docker Service Status

If Docker is still not working, check the status of the Docker service for any error messages:

### Check the status of Docker service
```bash
sudo systemctl status docker.service
```

## Step 8: Start Docker Again (if necessary)

If the Docker service is not running, try starting it again:

### Start Docker service
```bash
sudo systemctl start docker
```

## Step 9: Enable Docker to Start on Boot Again (if necessary)

Ensure Docker starts automatically on system boot:

### Enable Docker service to start on boot
```bash
sudo systemctl enable docker
```

## Step 10: Verify Docker Installation

Finally, verify that Docker is correctly installed and working by checking its version:

### Check Docker version
```bash
docker --version
```
This document summarizes the process to install Docker, enable it, and troubleshoot common installation issues on CentOS-based systems. If you face further issues, refer to the service status logs or Docker documentation for more advanced troubleshooting steps.
