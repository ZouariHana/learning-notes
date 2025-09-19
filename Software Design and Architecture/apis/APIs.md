# APIs in Software Engineering

APIs (Application Programming Interfaces) are the **contracts** that define how software components communicate with each other.  
They are central to **software design and architecture**, and they influence multiple quality attributes such as usability, maintainability, performance, and security.

---

## 1. What is an API?
- **Definition**: A set of rules and interfaces that allow one piece of software to interact with another.
- **Key idea**: Hides implementation details, exposes functionality.
- **Examples**:
  - Function calls in a programming library (e.g., `std::sort` in C++)  
  - Browser APIs (`fetch`, `localStorage`)  
  - Web service APIs (REST, GraphQL, gRPC)  

---

## 2. Levels of APIs
### Code-Level APIs
- Libraries and frameworks (C++ STL, Python standard library, Java SDK)
- Language-provided APIs (e.g., file I/O, threading)

### Application-Level APIs
- Internal module boundaries and class interfaces
- Clean abstractions in software architecture

### System-Level APIs
- External service interfaces (REST, GraphQL, gRPC, SOAP)
- SDKs for platforms (AWS SDK, Android SDK)
- Hardware and OS APIs (POSIX, Windows API)

---

## 3. API Design Principles
- Consistency → predictable naming, behavior
- Simplicity → easy to learn and use
- Abstraction → hide complexity, expose essentials
- Backward compatibility → don’t break existing clients
- Documentation → clear usage examples and reference

---

## 4. API Practices in Software Engineering
- **Versioning**: semantic versioning, URL versioning, compatibility
- **Security**: authentication (OAuth2, API keys), authorization, rate limiting
- **Testing**: unit tests for APIs, contract testing, integration testing
- **Documentation Tools**: Swagger / OpenAPI, JSDoc, Doxygen

---

## 5. APIs and the "-ilities"
- **Usability**: developer experience (DX) depends on clear, intuitive APIs
- **Maintainability**: good APIs reduce coupling and make systems easier to evolve
- **Portability**: APIs abstract away platform/hardware details
- **Performance**: API design affects latency, throughput, efficiency
- **Security**: APIs define the entry points to systems and must be protected

---

## 6. Common API Types
- **Browser APIs**: DOM, Fetch, Web Storage, WebRTC
- **Web APIs**: REST, GraphQL, gRPC
- **System APIs**: POSIX, Windows API, device drivers
- **Library APIs**: math libraries, machine learning libraries, graphics APIs (OpenGL, Vulkan)

---

## 7. Further Reading
- *Designing Evolvable Web APIs with ASP.NET* (or equivalent design-focused book)
- Martin Fowler on [API Design](https://martinfowler.com/articles/richardsonMaturityModel.html)
- Mozilla Developer Network (MDN) → [Web APIs](https://developer.mozilla.org/en-US/docs/Web/API)


```mermaid
mindmap
  root((APIs))
    Code-Level
      "Libraries & Frameworks"
      "Language APIs (File I/O, Threads)"
      "Standard Libraries (STL, Python stdlib)"
    Application-Level
      "Module Interfaces"
      "Class Interfaces"
      "Internal Abstractions"
    System-Level
      "Web APIs (REST, GraphQL, gRPC)"
      "SDKs (AWS, Android)"
      "OS APIs (POSIX, Windows API)"
      "Hardware APIs (Drivers, Bluetooth)"

```mermaid
mindmap
  root((Software Engineering))
    Software Design & Architecture
      APIs
        "Code-Level APIs"
        "Application-Level APIs"
        "System-Level APIs"
      "Design Patterns"
      "Modularity"
    Quality Attributes (-ilities)
      Performance
        "API design impacts latency & throughput"
      Usability
        "Developer Experience (DX)"
      Maintainability
        "Stable contracts reduce coupling"
      Security
        "APIs are system entry points"
      Portability
        "APIs abstract away platforms/hardware"
