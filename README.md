Parallel File Encryption/Decryption Tool
A high-performance C++ utility for secure file encryption and decryption using multi-processing, shared memory, and synchronization mechanisms.

Features
Parallel Processing: Utilizes multi-processing (fork, exec, wait) to distribute encryption/decryption tasks efficiently.

Shared Memory (mmap): Enables fast inter-process communication (IPC) for high-speed data access.

Thread-Safe Operations: Implements mutex locks and semaphores to prevent race conditions during file I/O.

Optimized Large File Handling: Splits workloads across child processes to maximize CPU utilization and reduce processing time.

Smart Pointers (RAII): Ensures automatic memory management, preventing leaks and improving stability.

Secure File I/O: Validates file integrity and includes robust exception handling for error recovery.

Custom Process Scheduling: Balances CPU load across processes for optimal performance.

Technical Implementation
1. Multi-Processing Architecture
Uses POSIX APIs (fork(), exec(), wait()) to spawn child processes for parallel task execution.

Each child process handles a chunk of the file, improving throughput for large files.

2. Shared Memory & Synchronization
mmap for Shared Memory: Allows processes to read/write encrypted data without costly IPC overhead.

Mutex Locks & Semaphores: Ensures safe concurrent access to shared resources (file buffers, status flags).

3. Performance Optimization
Dynamic Task Distribution: Assigns file chunks to idle processes for load balancing.

Smart Pointers (std::unique_ptr, std::shared_ptr): Automates memory cleanup, reducing manual management errors.

4. Security & Error Handling
File Integrity Checks: Validates input/output files before processing.

Exception Handling: Catches and logs errors (file access failures, memory allocation issues).