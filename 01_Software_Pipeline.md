# How Software Products Are Made

Writing code is just *one* part of the lifecycle. To really understand “how software products are made,” you need to see the whole pipeline:

---

## 1. Implementation (Code)
- Writing the actual source code in languages like C++, Python, JavaScript, etc.
- Organizing it into modules, classes, functions.

---

## 2. Compilation and Builds
- **Compilation**: Turning source code into something the machine can execute.  
  - C/C++ → `.exe` (Windows), ELF binaries (Linux), `.dylib` (Mac)  
  - Java → `.class` bytecode  
  - Web → transpilation/bundling (TypeScript → JavaScript, etc.)  
- **Build system**: A tool that automates compilation, linking, packaging (e.g., `make`, CMake, Gradle, Maven, npm).  
- **Build artifact**: The output of a build (binary, `.jar`, `.dll`, `.so`, `.wasm`, etc.).

---

## 3. Packaging
- `.msi` (Windows Installer), `.deb` (Debian/Ubuntu), `.rpm` (Red Hat), `.dmg` (macOS) are **installers/packages**.
- They contain:
  - Compiled program  
  - Dependencies  
  - Metadata (name, version, maintainer, permissions)  
  - Installation scripts (where to copy files, registry edits, system services, etc.)  
- In short: **They are built artifacts wrapped in a format the OS knows how to install and manage.**

---

## 4. Version Control
- Git, Mercurial, etc. → track history, collaborate, branch, and merge.  
- Versioning ties the code to a build artifact (e.g., `v1.2.3` → installer with same version).

---

## 5. Deployment
- **Web**: Deploy to servers, cloud, or CDNs → accessed via browser.  
- **Mobile**: Package into `.apk` (Android) or `.ipa` (iOS), then publish on app stores.  
- **Desktop**: Release `.msi`, `.dmg`, `.deb`, etc. for download.  

### CI/CD (Continuous Integration / Continuous Delivery)
- Builds automatically on every commit  
- Runs tests  
- Packages artifacts  
- Deploys to staging/production environments  

---

## Key Takeaway
A strong software engineer understands more than just writing code.  
You should know:
- **Build systems and packaging** (how source turns into software users can install)  
- **Version control** (for collaboration and history)  
- **Deployment & distribution** (so your code actually reaches users)  

You don’t need to be a full DevOps expert, but knowing the pipeline end-to-end makes you a stronger engineer.
