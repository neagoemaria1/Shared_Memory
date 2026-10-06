# Shared Memory and Semaphore Synchronization

A C++ project that demonstrates inter-process communication and synchronization using shared memory and semaphores.

The application creates a parent process and a child process that share and update the same integer value. Access to the shared memory is synchronized using a semaphore to prevent race conditions.

## Features

- Process creation using `fork()`
- Shared memory using `shm_open()` and `mmap()`
- Process synchronization using semaphores
- Critical section protection
- Parent-child process communication
- Shared data modification
- Resource cleanup after execution

## How It Works

The program creates a shared memory area containing an integer initialized to `1`.

A child process is created using `fork()`, and both the parent and child processes repeatedly access the shared value.

Before entering the critical section, each process locks the semaphore:

```cpp
sem_wait(semaphore);
```

After finishing the operation, the semaphore is released:

```cpp
sem_post(semaphore);
```

This ensures that only one process can access and modify the shared memory at a time.

The execution continues until the shared value reaches `1000`.

## Technologies

- C++
- Shared Memory
- Semaphores
- Inter-Process Communication
- Process Synchronization
- Linux System Programming

## Main Functions

The project uses:

- `fork()`
- `shm_open()`
- `ftruncate()`
- `mmap()`
- `sem_open()`
- `sem_wait()`
- `sem_post()`
- `waitpid()`
- `munmap()`
- `shm_unlink()`

## Project Purpose

The project demonstrates how multiple processes can safely communicate and modify shared data using shared memory and semaphore-based synchronization.
