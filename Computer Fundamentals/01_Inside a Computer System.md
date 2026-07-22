# Inside a Computer System | TryHackMe

> **Room:** Inside a Computer System  
> **Platform:** TryHackMe  
> **Difficulty:** Easy  
> **Learning Path:** Pre Security

---

# Overview

Before learning how to secure computer systems, it's important to understand how they work internally.

This room introduces the core components of a computer system, explains the purpose of each component, and demonstrates what happens behind the scenes when a computer is powered on.

Understanding these fundamentals builds the foundation for future cybersecurity topics such as operating systems, malware analysis, digital forensics, and penetration testing.

---

# Learning Objectives

After completing this room, I learned to:

- Identify the core components of a computer system.
- Understand the role of each hardware component.
- Explain the computer boot process.
- Understand how hardware components work together to start an operating system.

---

# Task 1 - Introduction

Before protecting a computer system, we first need to understand what we are protecting.

Just like defending a castle requires knowledge of its layout and important areas, defending a computer requires understanding its internal components and how they interact.

This room focuses on the fundamentals of computer hardware and the boot process.

---

# Task 2 - Inside a Computer System
<img width="1678" height="1118" alt="66c44fd9733427ea1181ad58-1770828504619" src="https://github.com/user-attachments/assets/fdf6663c-b7d4-438e-bade-dcb92253f4ff" />


Every computer consists of several essential hardware components, each performing a specific function.

TryHackMe uses an interactive exercise that compares computer components to parts of the human body, making it easier to understand their roles.

## CPU (Central Processing Unit)

The CPU is considered the **brain of the computer**.

It processes instructions, performs calculations, and controls communication between hardware components.

---

## RAM (Random Access Memory)

RAM is the computer's temporary working memory.

It stores data and applications currently being used by the CPU.

Unlike permanent storage, RAM loses its contents when the computer is powered off.

---

## Storage Device

Storage devices such as SSDs and HDDs permanently store data, including:

- Operating System
- Applications
- Documents
- Images
- Videos

Unlike RAM, stored data remains even after shutting down the computer.

---

## Motherboard

The motherboard connects all major hardware components together.

It enables communication between the CPU, RAM, storage devices, GPU, and other peripherals.

---

## Power Supply Unit (PSU)

The PSU supplies electrical power to every hardware component inside the computer.

Without it, none of the components can function.

---

## Graphics Processing Unit (GPU)

The GPU processes graphical data and renders images displayed on the monitor.

It is commonly used for:

- Gaming
- Video rendering
- Graphic design
- Artificial Intelligence
- Machine Learning

---

### Question

**Give in the flag you received after completing the exercise on the static site.**

### Answer

```text
THM{4llpccomp0n3nts1d3nt1f13d}
```

---

# Task 3 - What Happens When You Press the Start Button?

Starting a computer involves several important processes before the operating system loads.

This sequence is called the **boot process**.
<img width="1522" height="122" alt="66c44fd9733427ea1181ad58-1770828785615" src="https://github.com/user-attachments/assets/492daa16-227b-4a17-81c6-e8173c954ef5" />


---

## Step 1 - Power Button

Pressing the power button sends a signal to the Power Supply Unit (PSU), allowing electrical power to reach all hardware components.

---

## Step 2 - Firmware Starts

After power is supplied, the computer starts its firmware.

Modern computers use **UEFI (Unified Extensible Firmware Interface)**, while older systems use **BIOS (Basic Input/Output System)**.

The firmware initializes hardware and prepares the computer for startup.

---

## Step 3 - Power-On Self Test (POST)

The firmware performs the **Power-On Self Test (POST)** to verify that essential hardware components are functioning correctly.

This includes checking:

- CPU
- RAM
- Storage Devices
- Keyboard
- Other connected hardware

If any hardware issue is detected, the system reports an error before continuing.

---

## Step 4 - Select Boot Device

Once the hardware checks are complete, the firmware searches for a bootable device.

Common boot devices include:

- SSD
- HDD
- USB Drive
- DVD

The device with the highest priority containing an operating system is selected.

---

## Step 5 - Bootloader Starts

The bootloader is loaded from the selected storage device.

Its job is to load the operating system into RAM and transfer control from the firmware to the operating system.

After this process completes, the operating system starts normally.

---

### Question

**What is the flag that you received after completing the exercise?**

### Answer

```text
THM{pc5ucce55fully5t4rt3d}
```

---

# Task 4 - Conclusion

This room concludes by emphasizing that understanding computer hardware and the boot process is essential before moving on to more advanced cybersecurity concepts.

Many attacks target specific hardware components, operating systems, or the boot process itself, making these fundamentals important for both offensive and defensive security.

---

# Key Takeaways

After completing this room, I learned:

- The purpose of the CPU, RAM, Motherboard, GPU, Storage Devices, and PSU.
- How computer hardware components communicate with each other.
- The complete computer boot process.
- The role of UEFI/BIOS during startup.
- How the Power-On Self Test (POST) verifies hardware before loading the operating system.

---

# Conclusion

This room provides an excellent introduction to computer fundamentals and explains how a computer starts from the moment the power button is pressed until the operating system loads.

These concepts form the foundation for many cybersecurity topics and are essential knowledge for anyone beginning a career in information security.

---

## References

- TryHackMe – Inside a Computer System
- Computer Fundamentals
