# Virtual Machines (VMs)

## 1. What is a Virtual Machine?
A **Virtual Machine (VM)** is a software-based abstraction of a physical machine.  
It provides a **runtime environment** that executes programs as if they were running on dedicated hardware, but in reality, they are running on top of another system.

---

## 2. Types of Virtual Machines
- **System Virtual Machines**  
  - Emulate an entire physical machine, including CPU, memory, and devices.  
  - Allow running multiple operating systems on the same hardware.  
  - Examples: VMware, VirtualBox, QEMU, KVM.

- **Process Virtual Machines**  
  - Provide a runtime environment for a single program.  
  - Abstract away hardware/OS details, exposing a consistent execution model.  
  - Examples:  
    - **JVM (Java Virtual Machine)** → runs Java bytecode.  
    - **CLR (.NET Common Language Runtime)** → runs C#, F#, VB.NET.  
    - **WebAssembly runtimes** → run Wasm modules in a sandbox.

---

## 3. Why Virtual Machines Matter
- **Portability** → software can run on any platform with a compatible VM.  
- **Isolation** → VMs provide sandboxing and fault isolation.  
- **Security** → controlled environments limit access to host resources.  
- **Performance** → Just-In-Time (JIT) compilation and optimization at runtime.  
- **Flexibility** → enable cloud computing, containerization, and language runtimes.

---

## 4. Where VMs Fit in the Bigger Scheme
Virtual Machines sit at the **execution environment layer** of software engineering.  
They are part of the **software infrastructure** that bridges code and hardware.

- **Below applications**: Applications and services run on top of a VM.  
- **Above hardware**: VMs abstract away CPU, memory, and OS differences.  
- **Alongside operating systems**:  
  - System VMs can run entire OS instances.  
  - Process VMs run as programs inside an OS.

---

## 5. VMs and the Software Quality Attributes
- **Portability** → “write once, run anywhere.”  
- **Performance** → runtime optimization, JIT compilation.  
- **Security** → sandboxing, controlled execution.  
- **Maintainability** → stable execution environment across platforms.  
- **Scalability** → foundation of virtualization and cloud computing.  

---

## 6. Summary
Virtual Machines provide the **abstraction layer** that allows software to run independently of the underlying hardware and operating system.  
They are a cornerstone of modern computing, enabling cross-platform portability, cloud infrastructure, language runtimes, and secure execution environments.

