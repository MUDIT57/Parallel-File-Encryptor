# Parallel File Encryptor/Decryptor in C++

## 📄 Description

This project is a **C++-based tool** for performing **file encryption and decryption in parallel** using multiple processes. It focuses on **process-level concurrency**, **shared memory communication** (`mmap`), and uses **synchronization mechanisms** like **mutex locks** and **semaphores** to maintain thread-safe operations.

The tool is designed with the goal of improving performance when handling **large files** by dividing work across multiple child processes, each handling a specific portion of the file in parallel.

---

## 🧩 Key Features

- **Parallel processing** using `fork()` to spawn child processes.
- **Shared memory** using `mmap()` for inter-process communication.
- **Synchronization** using `pthread_mutex_t` and `sem_t` to ensure exclusive access to shared data.
- **Secure file I/O**, exception handling, and proper resource cleanup.
- **Custom task management** for controlling file segments and distributing load.
- **Smart pointers** (`std::unique_ptr`) used for safer memory management in non-shared regions.
- **POSIX-compliant** design targeting Linux-based systems.

---

## 🏗️ Build Instructions

### Requirements

- A POSIX-compliant OS (Linux/macOS)
- C++17-compatible compiler (`g++`, `clang++`)
- `make` or `cmake` (optional but recommended)

### Compilation

To build using a simple `Makefile`:

```bash
make
