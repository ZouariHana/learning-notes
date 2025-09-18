# Common Browser APIs

Modern browsers expose many APIs to web developers. Some are foundational and others are more specialized.  
Here are the most **common and widely used browser APIs**:

---

## 🔑 Core / Foundational APIs
- **DOM API (Document Object Model)** → read and manipulate HTML & CSS (`document.querySelector`, `element.style`, etc.)
- **CSSOM API (CSS Object Model)** → programmatic access to CSS rules and styles
- **Fetch / XMLHttpRequest** → network requests to servers (REST, GraphQL, etc.)
- **Console API** → debugging (`console.log`, `console.error`, etc.)

---

## 📂 Storage APIs
- **Local Storage / Session Storage** → simple key–value storage in the browser
- **IndexedDB** → structured database for larger datasets
- **Cookies API** → though usually set via HTTP headers, JS can read/write them (`document.cookie`)

---

## 🖱️ Input & Interaction APIs
- **Events API** → listening to clicks, keyboard, mouse, scroll, etc.
- **Drag & Drop API** → implement file drag/drop and reordering
- **Clipboard API** → copy/paste text or data
- **Pointer Lock & Fullscreen APIs** → control immersive interactions (games, viewers)

---

## 📷 Device & Hardware APIs
- **Geolocation API** → access user location (with permission)
- **MediaDevices / getUserMedia** → camera & microphone access
- **WebUSB / WebBluetooth / WebSerial** → connect to hardware devices
- **Device Orientation & Motion APIs** → mobile sensors like accelerometer/gyroscope

---

## 🎨 Graphics & Audio APIs
- **Canvas API** → draw and manipulate graphics programmatically
- **WebGL / WebGPU** → 2D/3D rendering with GPU acceleration
- **SVG API** → manipulate scalable vector graphics
- **Web Audio API** → sound generation, processing, effects

---

## 🔒 Security & Identity APIs
- **Credential Management API** → manage passwords and federated login
- **WebAuthn (Web Authentication API)** → passwordless login with biometrics/security keys
- **Permissions API** → query or request user permissions (camera, location, etc.)

---

## 📨 Communication APIs
- **WebSockets** → real-time, two-way communication
- **Server-Sent Events (SSE)** → one-way push from server to browser
- **WebRTC** → real-time peer-to-peer video, audio, and data channels
- **BroadcastChannel API** → communication between browser tabs/windows of the same origin

---

## ⚙️ Performance & Background Work
- **Web Workers** → run scripts in background threads
- **Service Workers** → power Progressive Web Apps (offline, caching, push notifications)
- **Performance API** → measure load times, runtime metrics
- **Battery API** (deprecated in some browsers for privacy, but still notable historically)

---

## 👉 Most Common in Daily Web Development
- **DOM, Events, Fetch, LocalStorage, Canvas, WebSockets, Service Workers, Geolocation, MediaDevices**
