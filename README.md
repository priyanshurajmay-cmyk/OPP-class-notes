# Map of Computer Science Notes 

## 1. Theoretical Computer Science 
  
The foundation of computing, dealing with logic and mathematics. 

### Algorithms & Data Structures
- **Algorithms:**
  - **Search:** Linear, Binary
  - **Sort:** Bubble Sort, Merge Sort
  - **Graph Theory**
- **Analysis of Algorithms (Complexity):**
  - Big O Notation: $O(1)$, $O(\log n)$, $O(n)$, $O(n \log n)$, $O(n^2)$, $O(2^n)$, $O(n!)$
- **Data Structures:**
  - Arrays, Trees, Graphs, Hash Tables, Linked Lists

### Computability Theory
- **Turing Machine:** The abstract model of computation.
- **Lambda Calculus**
- **Automata Theory**
- **Formal Languages**

### Computational Complexity
- **P vs NP:** The central open question.
- **Complexity Classes:**
  - P (Polynomial time)
  - NP (Nondeterministic Polynomial time)
  - NP-Complete
  - NP-Hard

### Information Theory & Cryptography
- **Information Theory:**
  - Compression
  - Error Correction
  - Entropy
  - Parity Checking
- **Cryptography:**
  - Public Key
  - Private Key

---

## 2. Computer Engineering

The bridge between theoretical concepts and physical hardware.

### Hardware
- **Core Components:**
  - CPU (Central Processing Unit)
  - RAM (Random Access Memory)
  - SSD (Solid State Drive)
  - Motherboard
  - Power Supply
  - Monitor

### Computer Architecture
- **CPU Internals:**
  - Control Unit
  - Arithmetic/Logic Unit (ALU)
  - Memory
- **System Design:**
  - Multiprocessors
  - FPGA (Field-Programmable Gate Array)
  - Logic Blocks, Interconnections

### Operating Systems
- Manages hardware and software resources.
- **Examples:** iOS, macOS, Windows, Linux
- **Concepts:**
  - Scheduling & Processes
  - Networking
  - Distributed/Parallel Systems

### Software & Programming Languages
- **Language Levels:**
  - High-Level (Python, Java, C++)
  - Assembly Language
  - Machine Code
- **Tools:**
  - **Compiler:** Translates high-level code to machine code.
  - **Assembler:** Translates assembly code to machine code.

### Software Engineering
- The systematic approach to designing, developing, and maintaining software.
- **Methodologies:** Agile, Scrum, Kanban
- **Practices:**
  - Version Control (e.g., Git)
  - Testing
  - Object-Oriented Design

---

## 3. Applications

The practical use of computer science and engineering to solve real-world problems.

### Artificial Intelligence (AI)
- **Machine Learning:**
  - Supervised & Unsupervised Learning
  - Neural Networks, Deep Learning
- **Natural Language Processing (NLP):**
  - Chatbots, Knowledge Representation
- **Computer Vision:**
  - Image Processing
- **Other areas:** Robotics, Optimisation, Boolean Satisfiability (SAT)

### Graphics & Visualization
- **Computer Graphics**
- **Virtual Reality (VR)**
- **Augmented Reality (AR)**
- **Human-Computer Interaction (HCI)**

### Data & Computational Science
- **Data Management:**
  - Databases, SQL, Data Warehouses
- **Big Data**
- **Computational Science:**
  - Simulation
  - Bioinformatics
  - Computational Chemistry/Physics
  - Numerical Analysis

### Networking & Security
- **Internet of Things (IoT)**
- **Hacking** (Cybersecurity)

### High-Performance Computing
- **Super Computing**
- **Performance Analysis & Benchmarking**

# CPU vs. GPU vs. TPU: A Comparison

## 1. Memory Subsystem Architecture

How each processor manages its memory hierarchy.

### CPU
- **Management:** Implicitly managed by hardware.
- **Hierarchy:**
  - L3 Cache
  - L2 Cache
  - L1 Data (L1D) & L1 Instruction (L1I) Caches

### GPU
- **Management:** Mixed (partly hardware, partly software).
- **Hierarchy:**
  - L2 Cache
  - Streaming Multiprocessors (SM) containing:
    - L1/Texture (L1/TX) Cache
    - Register Files (RF)

### 'TPU' (Tensor Processing Unit)
- **Management:** Explicitly managed by software.
- **Components:**
  - Activation Buffer
  - Weight FIFO (First-In, First-Out)
  - Accumulator Register File

---

## 2. Compute Primitive

The smallest unit of data each processor is designed to operate on.

### CPU: Scalar
- Operates on a single data point at a time (e.g., `5 + 3`).

### GPU: Vector
- Operates on a one-dimensional array of data at a time (e.g., a row or column of numbers).

### TPU: Tensor (Matrix)
- Operates on a two-dimensional array (or matrix) of data at a time.

# Types of Memory and Storage

## 1. Memory (Primary, Volatile)

### RAM (Random Access Memory)
- **SRAM (Static RAM)**
  - Used for CPU caches.
  - Faster than DRAM.
- **DRAM (Dynamic RAM)**
  - **SDRAM** (Synchronous DRAM)
  - **DDR SDRAM** (Double Data Rate SDRAM)
    - DDR4
    - DDR5
  - **GDDR SDRAM** (Graphics DDR SDRAM)

### ROM (Read-Only Memory)
- Used for storing essential system instructions.
- **Firmware**
- **BIOS**

## 2. Storage (Secondary, Non-Volatile)

- **HDD** (Hard Disk Drive)
- **SSD** (Solid State Drive)
- **USB Drive**
- **SD Card**

# Computing Hardware & Architectures

---

### CPU (Central Processing Unit)
The **main processor** or "brain" of a computer. It handles all general-purpose tasks and instructions for the system.

---

### GPU (Graphics Processing Unit)
A **specialized processor** designed for parallel processing. It excels at tasks with many simultaneous calculations, like rendering graphics, video editing, and AI computations.

---

### APU (Accelerated Processing Unit)
A single chip that **combines a CPU and a GPU** on the same die. This integrated design is common in laptops and budget-friendly systems.

---

### FPGA (Field-Programmable Gate Array)
An integrated circuit that can be **programmed or reconfigured after it's manufactured**. It offers high performance and flexibility for specialized tasks.

---

### AI Accelerators
Hardware specifically designed to **speed up artificial intelligence (AI) and machine learning (ML) applications**. Examples include Google's TPU (Tensor Processing Unit) and NPUs (Neural Processing Units).

---

### RISC-V
A **free and open-source instruction set architecture (ISA)**. It provides an open standard for designing processors, competing with proprietary architectures like x86 and ARM.

# The Life of a DNS Query

### The Process

1.  **User Request:** You want to visit `example.com`. Your **Browser** needs to find the server's IP address.

2.  **Browser & Resolver Cache Check:**
    - The **Browser** first checks its own cache.
    - If not found, it asks the system's DNS **Resolver** (e.g., your ISP's server).
    - The **Resolver** also checks its cache. If the address is not cached, the search begins.

3.  **Query the Root Nameserver:**
    - The **Resolver** asks a **Root Nameserver** for the IP of `example.com`.
    - The Root Server doesn't know the IP, but it knows who handles all `.com` domains and refers the Resolver there.

4.  **Query the TLD Nameserver:**
    - The **Resolver** now asks the **`.com` Top-Level Domain (TLD) Nameserver**.
    - The TLD server doesn't know the final IP, but it knows which nameserver is the authority for `example.com`. It refers the Resolver to that server.

5.  **Query the Authoritative Nameserver:**
    - The **Resolver** asks the `example.com` **Authoritative Nameserver**.
    - This server is the final authority for the domain and knows the IP address. It responds with the IP (`93.184.216.34`).

6.  **Final Response:**
    - The **Resolver** receives the IP address and sends it back to your **Browser**.
    - The **Browser** can now send its HTTP request directly to the server at `93.184.216.34` to load the website.

# Programming Language Performance Comparison

### Language Type Key
- `(c)`: Compiled Language
- `(v)`: Virtual Machine / JIT Language
- `(i)`: Interpreted Language

---

### Table 1: Energy Usage (Normalized)
*(Lower is more energy-efficient)*

| Rank | Language      | Score  |
| :--- | :------------ | :----- |
| 1    | (c) C         | 1.00   |
| 2    | (c) Rust      | 1.03   |
| 3    | (c) C++       | 1.34   |
| 4    | (c) Ada       | 1.70   |
| 5    | (v) Java      | 1.98   |
| ...  | ...           | ...    |
| 25   | (i) Python    | 75.88  |
| 26   | (i) Perl      | 79.58  |

---

### Table 2: Execution Time (Normalized)
*(Lower is faster)*

| Rank | Language      | Score  |
| :--- | :------------ | :----- |
| 1    | (c) C         | 1.00   |
| 2    | (c) Rust      | 1.04   |
| 3    | (c) C++       | 1.56   |
| 4    | (c) Ada       | 1.85   |
| 5    | (v) Java      | 1.89   |
| ...  | ...           | ...    |
| 25   | (i) Python    | 71.90  |
| 26   | (i) Lua       | 82.91  |

---

### Table 3: Memory Usage (Normalized)
*(Lower is less memory-intensive)*

| Rank | Language      | Score  |
| :--- | :------------ | :----- |
| 1    | (c) Pascal    | 1.00   |
| 2    | (c) Go        | 1.05   |
| 3    | (c) C         | 1.17   |
| 4    | (c) Fortran   | 1.24   |
| 5    | (c) C++       | 1.34   |
| ...  | ...           | ...    |
| 25   | (v) Erlang    | 7.20   |
| 26   | (i) Dart      | 19.84  |

### Key Observations
- **Compiled languages** like C, Rust, and C++ are consistently the top performers in energy efficiency, speed, and memory usage.
- **Interpreted languages** like Python, Perl, and Ruby tend to be the most resource-intensive.
- **Virtual Machine languages** like Java and C# offer a middle ground in performance.

# The Memory & Storage Hierarchy

This hierarchy illustrates the trade-off between speed, size, and cost in computer memory and storage technologies.

-   **Top of Pyramid:** Faster, smaller, higher-cost
-   **Bottom of Pyramid:** Slower, larger, lower-cost

---

### 1. On-Chip Memory (Fastest)
The memory located directly on the CPU chip.
-   **Registers:** The fastest possible memory, holds data the CPU is currently processing.
-   **Cache:** A small, extremely fast memory buffer between the CPU and main memory (DRAM).

### 2. Main Memory
The primary workspace for the computer.
-   **DRAM (RAM):** Where the operating system and running applications are loaded. It is volatile, meaning it loses data when power is off.

### 3. Storage (Slowest)
Long-term, non-volatile storage that retains data without power.
-   **Persistent Memory:** Blends the speed of RAM with the persistence of storage.
-   **CXL Memory:** A type of memory expansion that connects over the high-speed CXL bus.
-   **SSD (Solid State Drive):** Fast storage with no moving parts.
-   **HDD (Hard Disk Drive):** Slower, mechanical storage offering large capacities at a low cost.

# The 7 Layers of the OSI Model

A conceptual framework for understanding network interactions in seven distinct layers.

---

### Software Layers
*Layers that primarily deal with application data and representation.*

-   **7. Application Layer:** Provides network services directly to user applications (e.g., web browser, email).
-   **6. Presentation Layer:** Responsible for data translation, encryption, and compression.
-   **5. Session Layer:** Manages, opens, and closes communication sessions between two devices.

---

### Heart of OSI
*The bridge between the software and hardware layers.*

-   **4. Transport Layer:** Provides reliable end-to-end data transfer and error control (e.g., TCP & UDP).

---

### Hardware Layers
*Layers that handle the transmission of data over the physical network.*

# Simplified Computer Architecture Overview
---

### 1. CPU (Central Processing Unit)
- The "brain" of the computer that performs calculations.
- This diagram shows a system with two CPUs (or two cores).

### 2. Cache Memory
*A system of very fast memory located close to the CPU to speed up access to frequently used data.*

- **L1 & L2 Cache:**
  - Each CPU core has its own private L1 and L2 cache.
  - These are the fastest and smallest levels of cache.

- **L3 Cache:**
  - A larger cache that is **shared** between both CPUs.
  - Slower than L1/L2, but faster than RAM.

### 3. RAM (Main Memory)
- The computer's main workspace for the operating system, running programs, and current data.
- It is a shared resource for all CPU cores.

### 4. Storage and I/O
*Slower, long-term components for data persistence and communication.*

- **Hard Disk / SSD:** Used for permanent storage of files and the operating system.
- **Network Card (NIC):** Allows the computer to communicate with other devices over a network.

# A Guide to the Linux Filesystem Hierarchy

---

### `/bin` - Binaries
Contains essential executable programs used by **all users** on the system.

---

### `/boot` - Boot Files
Contains all the configurations and files needed to **boot the system's kernel**.

---

### `/dev` - Device Files
Contains special files that represent physical and virtual **devices** attached to the system.

---

### `/etc` - Configuration
Holds system-wide and application-level **configuration files**.

---

### `/home` - User Directories
Contains the personal **home directories for non-root users**.

---

### `/lib`, `/lib32`, `/lib64` - Libraries
Stores essential shared **library files** required by system binaries. The numbered folders are for different system architectures (32-bit and 64-bit).

---

### `/lost+found` - Recovered Files
When files are lost due to an error (like a sudden power outage), they may be **recovered and stored here**.

---

### `/media` - Removable Media
A common directory where some systems **auto-mount external devices** like USB drives.

---

### `/mnt` - Mount Point
A temporary **mount point** for manually mounting filesystems or devices.

---

### `/opt` - Optional Packages
A directory for installing **optional, third-party software** that isn't part of the standard system.

---

### `/proc` - Process Filesystem
A virtual filesystem that provides real-time information about system **processes and resources**.

---

### `/root` - Root's Home
The personal **home directory for the `root` user** (the system administrator).

---

### `/sbin` - System Binaries
Contains essential executables used specifically for **system administration** by the root user.

---

### `/tmp` - Temporary Files
A place for storing **temporary files**. These are importantly **removed after every reboot**.

---

### `/usr` - User Programs
Contains user-related programs, libraries, documentation, and other read-only data. Think of it as **"User System Resources."**

---

### `/var` - Variable Files
Stores **variable data files** that are expected to change during operation, such as logs, caches, and spools.

-   **3. Network Layer:** Handles packet routing, including logical addressing (IP addresses).
-   **2. Data Link Layer:** Manages physical addressing (MAC addresses) and controls access to the physical medium.
-   **1. Physical Layer:** Transmits raw data bits over the physical network medium (e.g., cables, radio waves).

# How NAT (Network Address Translation) Works

**NAT** is the process that allows multiple devices on a private network to share a single public IP address to communicate with the internet.

### The Step-by-Step Process

1.  **Request from a Private Device:**
    - A computer on a local network wants to contact a server on the internet (e.g., `example.com`).
    - This computer has a **Private IP** address that only works within the local network (e.g., `10.10.0.5`).
    - The request is sent to the local network's router.

2.  **Router Translates the Address:**
    - The router receives the request.
    - It changes the packet's source address from the computer's **Private IP** to its own **Public IP** (e.g., `27.43.84.12`), which is visible to the internet.
    - The router keeps a record of this change in a NAT table.

3.  **Request Reaches the Server:**
    - The request travels over the internet.
    - The destination server (`example.com`) receives the request and sees it as coming from the router's **Public IP**. The server has no knowledge of the original private address.

4.  **The Return Trip:**
    - The server sends its response back to the router's public IP address.
    - The router checks its NAT table, sees which private device the response is for, and forwards it to the correct computer (`10.10.0.5`).

# Notes on Python and CS Fundamentals

---

## 1. How Code Becomes a Program

Different languages have different processes for turning human-readable code into machine instructions.

### How Python Works (An Interpreted Language)
Python uses a multi-stage process involving both a compiler and an interpreter (within a Virtual Machine).

1.  **Source Code:** You write your code in a `.py` file.
2.  **Compiler:** The Python compiler translates your source code into an intermediate language called **Bytecode** (saved as `.pyc` files).
3.  **Python Virtual Machine (PVM):** This is the core of Python. The PVM takes the bytecode and interprets it, converting it into machine code that the CPU can execute.
4.  **Running Program:** The machine code is executed, and your program runs.

### How C Works (A Compiled Language)
C code goes through a multi-step compilation process to create a direct executable file.

1.  **Preprocessor:** Reads the source code (`.c`), includes header files (`.h`), and produces an intermediate file (`.i`).
2.  **Compiler:** Compiles the intermediate file into **Assembly Code** (`.s`).
3.  **Assembler:** Converts the assembly code into a machine-readable **Object File** (`.obj`).
4.  **Linker:** Combines the object file with necessary library files to create the final **Executable File** (`.exe`).

---

## 2. A Complete Python Learning Roadmap

This roadmap combines the key stages for learning Python from beginner to advanced.

### Stage 1: The Basics
- **Basic Syntax:** Learn the fundamental rules of the language.
- **Variables & Data Types:** `int`, `float`, `string`, `bool`.
- **Operators:** Arithmetic (`+`, `-`), Assignment (`=`), Comparison (`==`, `>`), Logical (`and`, `or`).
- **Conditionals:** `if`, `elif`, `else` statements.
- **Loops:** `for` and `while` loops.
- **Core Data Structures:** `Lists`, `Tuples`, `Sets`, `Dictionaries`.
- **Functions:** Defining and calling reusable blocks of code.
- **Exception Handling:** Using `try...except` blocks to manage errors.

### Stage 2: Data Structures & Algorithms (DSA)
- **Linear Structures:** Arrays, Linked Lists, Stacks, Queues.
- **Non-Linear Structures:** Hash Tables, Heaps, Binary Search Trees.
- **Algorithms:** Recursion, Sorting Algorithms (e.g., Bubble, Merge, Quick Sort).

### Stage 3: Object-Oriented Programming (OOP)
- **Classes:** Blueprints for creating objects.
- **Methods:** Functions that belong to a class.
- **Inheritance:** Creating new classes that reuse and extend existing ones.

### Stage 4: Advanced Topics
- **List Comprehensions:** Concise way to create lists.
- **Lambdas:** Small, anonymous functions.
- **Generators & Iterators:** Efficient ways to work with large sequences of data.
- **Decorators:** Functions that modify other functions.
- **Regular Expressions (Regex):** For powerful string searching and manipulation.
- **Threading:** For running multiple tasks concurrently.

### Stage 5: Essential Tools & Specializations
- **Package Managers:** Use **pip** or **conda** to install and manage libraries.
- **Version Control:** Learn **Git** for tracking changes to your code.
- **Testing:** Write tests for your code using frameworks like **pytest** or the built-in `unittest`.
- **Web Frameworks:** Build web applications with **Django**, **Flask**, or **FastAPI**.
- **Data Science:** Analyze data with libraries like **NumPy**, **Pandas**, and build models with **Scikit-learn**, **TensorFlow**, or **PyTorch**.
- **Automation:** Write scripts for tasks like **Web Scraping** or **GUI Automation**.

---

## 3. A Deep Dive into Data Structures

Data structures are fundamental to programming and are classified into several types.

### General Classification
- **Primitive:** The most basic data types.
  - `Integer`, `Float`, `String`, `Boolean`
- **Non-Primitive:** More complex structures derived from primitive types.
  - **Linear:** Data is arranged sequentially (e.g., `Stacks`, `Queues`).
  - **Non-Linear:** Data is arranged hierarchically or interconnected (e.g., `Graphs`, `Trees`).

### Python's Data Structures
- **Built-in Structures:**
  - **Lists:** **Mutable** (changeable), ordered sequences. `my_list = []`
  - **Tuples:** **Immutable** (unchangeable), ordered sequences. `my_tuple = ()`
  - **Dictionaries:** Store data in **key-value pairs**. They are unordered (in older Python versions) and mutable. `my_dict = {}`
  - **Sets:** Unordered collections of **unique** items. `my_set = set()`

- **User-Defined Structures:**
  - You can implement these using classes and objects.
  - **Linear:** `Linked Lists`, `Stacks`, `Queues`.
  - **Non-Linear:** `Trees`, `Graphs`, `Hash Tables`.

 # Core Computer Science & Python Notes

This document summarizes fundamental computer science concepts, including data structures, OOP, and key Python features.

---

## 1. Fundamental Concepts 

### Program vs. Process vs. Thread

-   **Program:** A passive file containing a set of instructions, stored on a disk (e.g., `Word.app`). It's not doing anything until you run it. -   **Process:** An instance of a program that is actively running in memory (RAM). When you double-click a program, you create a process. A single program can have multiple processes running at once.
-   **Thread:** The smallest unit of execution within a process. A single process can have multiple threads, allowing it to perform different tasks at the same time (e.g., one thread in your browser downloads an image while another lets you keep scrolling).

---

## 2. Data Structures 

Data structures are formats for organizing, managing, and storing data.

### Classification of Data Structures

-   **Linear Data Structures:** Elements are arranged in a sequential order.
    -   **Array:** Stores elements in a continuous block of memory, accessed by an index. Fixed in size.
    -   **Linked List:** Stores elements in "nodes," where each node contains data and a pointer to the next node. Flexible in size.
    -   **Stack:** A **Last-In, First-Out (LIFO)** structure. Think of a stack of plates—you add to the top and remove from the top.
    -   **Queue:** A **First-In, First-Out (FIFO)** structure. Think of a line at a store—the first one in is the first one out.
-   **Non-linear Data Structures:** Elements are arranged in a hierarchical or networked manner.
    -   **Tree:** Organizes data in a parent-child hierarchy, like a family tree.
    -   **Graph:** Represents relationships between objects using nodes (vertices) and connections (edges), like a social network.
    -   **Hash Table:** Stores data as key-value pairs for extremely fast lookups using a hash function.

---

## 3. Object-Oriented Programming (OOP) 

OOP is a programming paradigm based on the concept of "objects."

-   **Class:** A blueprint or template for creating objects.
-   **Object:** An instance of a class; a concrete entity created from the blueprint.
-   **Encapsulation:** Bundling data (attributes) and methods (functions) that work on the data into a single unit (an object).
-   **Abstraction:** Hiding the complex implementation details and showing only the necessary features of an object.
-   **Inheritance:** Allowing a new class to inherit properties and methods from an existing class.
-   **Polymorphism:** The ability for something to take on many forms. For example, the `+` operator can perform addition on numbers and concatenation on strings.

---

## 4. Python Fundamentals 

Key building blocks for writing code in Python.

### Functions
A function is a reusable block of code that performs a specific task.

-   **Normal Function:** A named function defined with the `def` keyword.
    -   **Syntax:** `def function_name(parameter1, parameter2):`
    -   It has a name, parameters, a body, and can `return` a value.
-   **Lambda Function:** A small, anonymous (unnamed) function.
    -   **Syntax:** `lambda arguments: expression`
    -   It's limited to a single expression and is useful for short, simple operations.

### Common Built-in Functions & Keywords

| Function/Keyword | Description                               |
| :--------------- | :---------------------------------------- |
| `print()`        | Displays text or variables to the console |
| `len()`          | Gets the length of an object (like a list)|
| `input()`        | Receives input from the user              |
| `range()`        | Generates a sequence of numbers           |
| `int()`, `str()` | Convert values to integer or string       |
| `if...else`      | Executes code based on a condition        |
| `for`/`while`    | Loops to iterate over elements            |

### Common List Methods
Methods are functions that belong to an object (in this case, a list).

| Method            | Description                                   | Example `[1, 2, 3]`     |
| :---------------- | :-------------------------------------------- | :---------------------- |
| `.append(4)`      | Adds an element to the end of the list        | `[1, 2, 3, 4]`          |
| `.sort()`         | Sorts the list in place                       | `[1, 2, 3]` (if unsorted)|
| `.pop(1)`         | Removes and returns the element at an index   | `[1, 3]`                |
| `.remove(2)`      | Removes the first occurrence of a value       | `[1, 3]`                |
| `.reverse()`      | Reverses the list in place                    | `[3, 2, 1]`             |
| `.clear()`        | Removes all elements from the list            | `[]`                    |
