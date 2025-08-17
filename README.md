# Screen Casting Application in Rust

This project implements a cross-platform screen casting application developed in Rust, capable of capturing the content of a computer screen (either in full or a selected area) and streaming it in real time to connected peers. The application is designed to be lightweight, modular, and performant, with compatibility across Windows, macOS, and Linux.

The project was developed in response to a technical assignment focused on real-time multimedia systems, with the goal of designing and building a complete and extensible solution for desktop screen sharing. The core requirements were to implement a dual-mode system (caster and receiver), provide a user-friendly interface, and support real-time transmission with optional interaction and recording features.

---

## Objectives and Requirements

The implementation adheres to the following specifications:

### 1. Platform Support
The system is fully compatible with major desktop operating systems: **Windows**, **macOS**, and **Linux**. Platform abstraction layers were implemented to handle screen capture and input across different environments.

### 2. Operating Modes
The application can be launched in one of two distinct modes:

- **Caster Mode**: Streams the captured screen content to one or more peers.
- **Receiver Mode**: Connects to a remote caster and displays the incoming stream.

Mode selection is handled at runtime via the user interface.

### 3. Screen Area Selection
In caster mode, users can define a custom rectangular area of the screen to capture, allowing selective sharing instead of full-screen transmission.

### 4. Hotkey Integration
The system supports customizable keyboard shortcuts for:

- Pausing/resuming the stream
- Temporarily blanking the screen
- Terminating the session

These shortcuts are processed asynchronously to avoid blocking the streaming pipeline.

### 5. Annotation Tools *(Bonus Feature)*
A transparent overlay can be activated during casting to enable basic annotations over the stream. This includes drawing tools, text insertion, and highlight markers, implemented with minimal overhead to preserve performance.

### 6. Stream Recording *(Bonus Feature)*
When operating as a receiver, the system provides the option to record the incoming stream locally. The resulting video can be saved in standard formats for later playback.

### 7. Multi-Monitor Support *(Bonus Feature)*
The application is capable of detecting multiple connected displays and allows the user to select the target monitor from which to capture content.

---

## System Architecture

The project follows a modular design pattern, with components loosely coupled and organized for maintainability and future extension. Key architectural modules include:

- **Display Management**: Handles screen enumeration, capture routines, and monitor selection.
- **Networking Layer**: Manages peer-to-peer communication for broadcasting and receiving streams, supporting low-latency transmission.
- **Input Handling**: Processes keyboard shortcuts and UI inputs in a responsive manner.
- **Annotation Engine**: Draws interactive overlays on top of the video stream with minimal impact on frame rate.
- **Stream Controller**: Coordinates the overall application lifecycle, switching between modes and controlling session states.

The codebase is structured to separate platform-specific implementations from core logic, ensuring portability and cleaner maintenance.

---

## Technologies Used

- **Rust** as the main programming language, for its safety guarantees, concurrency model, and performance.
- **Cross-platform system APIs** for screen capture and monitor management
- **Custom lightweight GUI** for mode selection and settings configuration
- **Real-time data processing pipelines** for screen encoding and transmission
- **Modular file structure** to separate logic by function (streaming, UI, capture, recording, etc.)

---

## Project Scope and Status

The application implements all mandatory requirements and selected bonus features as defined in the original technical specification. While functional and stable, the project is still subject to code review and potential refactoring. Additional improvements considered for future versions include:

- WebRTC integration for higher-quality and more scalable streaming
- Support for mobile platforms (Android/iOS)
- Secure encrypted transmission and authentication mechanisms

