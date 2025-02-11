# LoRa Smart Agriculture System 🌾🌱

<p align="center">
  <a href="your-build-link"><img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build Status"></a>
  <a href="your-license-link"><img src="https://img.shields.io/badge/license-MIT-blue" alt="License"></a>
  <a href="your-docs-link"><img src="https://img.shields.io/badge/docs-latest-blue" alt="Documentation"></a>
  <a href="your-spring-boot-link"><img src="https://img.shields.io/badge/Spring%20Boot-🚀-orange" alt="Spring Boot"></a>
  <a href="your-emq-link"><img src="https://img.shields.io/badge/EMQ-📈-blue" alt="EMQ"></a>
  <a href="your-vue3-link"><img src="https://img.shields.io/badge/Vue3-📊-green" alt="Vue3"></a>
  <a href="your-mybatis-link"><img src="https://img.shields.io/badge/MyBatis-📚-orange" alt="MyBatis"></a>
  <a href="your-design-pattern-link"><img src="https://img.shields.io/badge/Design%20Patterns-🛠️-yellow" alt="Design Patterns"></a>
</p>

<p align="center">
  <a href="your-docs-link">📚 Documentation</a> |
  <a href="your-installation-link">🔧 Installation</a> |
  <a href="your-features-link">🌟 Features</a> |
  <a href="your-updates-link">📝 Updates</a> |
  <a href="your-contribute-link">🤝 Contribute</a>
</p>

## Introduction 📚

The LoRa Smart Agriculture System is an innovative IoT architecture designed for heterogeneous sensor integration and intelligent automation. It is guided by three core technological principles that define its uniqueness and flexibility:

- **Software-Defined Hardware**: Dynamic configuration files define hardware behavior, allowing flexible adjustments and extensions of hardware functions.
- **Separation of Business and Execution Flows**: Decouples business logic from execution processes, enhancing system flexibility and maintainability.
- **Metadata Programming**: Drives system logic with metadata, standardizing device abstraction, interaction rules, and data standards.

## Core Technological Principles 🔩

### 1. Software-Defined Hardware 🛠️

Hardware behavior (including when and how devices interact and function definitions) is dynamically defined via configuration files, rather than being hard-coded into software or hardware.

**Implementation** 📝

- **Application Configuration Files**: Define interaction rules between sensors and devices, such as trigger conditions and collaborative workflows.
- **Plugin Description Files**: Dynamically register hardware functions, enabling hot-swapping and seamless hardware integration.

**Advantages** 🌟

- Enhances the system's ability to adapt to diverse agricultural scenarios.
- Accelerates the integration of new devices, reducing development and maintenance costs.
- Builds a scalable architecture that supports future technological upgrades and hardware developments.

---

### 2. Separation of Business and Execution Flows 🔄

By decoupling business logic ("what to do") from execution processes ("how to do"), the system avoids the limitations of traditional architectures where business logic is embedded in hardware operations. This design promotes collaboration and enhances flexibility.

**Implementation** 📊

- Business flow focuses on describing system logic and goals.
- Execution flow handles device drivers and underlying command execution, ensuring hardware operation compatibility.

**Advantages** 🌟

- Allows business logic to adjust with metadata updates while maintaining the stability of the logic framework.
- Simplifies the development process, reduces hard-coded dependencies, and enhances system configurability and scalability.
- Provides unified foundational support, covering business flow, execution flow, and hardware abstraction.

---

### 3. Metadata Programming 📊

Metadata-driven system logic is the foundational support for implementing software-defined hardware and separating business and execution flows. Metadata encapsulates the core information required for system operation.

**Key Metadata Elements** 🔑

1. **Plugin Description Files**: Abstract hardware within software, supporting dynamic registration and operation of various devices.
2. **Application Configuration Files**: Define collaboration rules between hardware components for seamless interaction.
3. **Schema Files**: Standardize data formats and command structures, ensuring system-wide standardization.
4. **Transformation Files**: Achieve compatibility between external devices and the system through standardized integration.

**Advantages** 🌟

- Allows business logic to adjust with metadata updates while maintaining the stability of the logic framework.
- Simplifies the development process, reduces hard-coded dependencies, and enhances system configurability and scalability.
- Provides unified foundational support, covering business flow, execution flow, and hardware abstraction.

## Implementation Plan 📈

![](doc/images/achievement-en.png)

### Business Flow 📊

- **Instruction Interpretation Unit**: Converts configuration files into objects, parsing their content and storing them as data structures recognizable by the system.
- **Proxy Factory**: Generates proxy objects based on configuration files, containing all business information, including hardware collaboration rules.
- **Adaptive Code Generator**: Generates control code for proxy objects, implementing the specific logic operations of the business flow.

### Execution Flow 🔄

- **Plugin Layer**: Abstracts hardware as plugins, managed uniformly by the plugin management layer.
- **Hardware Abstraction Layer (HAL)**: Defines standardized APIs for hardware, called by the plugin layer.
- **Hardware Plugin Layer (HPL)**: Encapsulates driver code and functionality implementations for specific hardware.
- **Communication Layer**: Achieves efficient communication between software and hardware based on the MQTT protocol.

### Data Formats and Compatibility 📈

- **Schema Encoder**: Converts external device data into system Schema format.
- **Schema Decoder**: Converts system-generated data into formats compatible with external devices.
- **Data Transformation Files**: Define mapping rules between external and internal data formats.

---

## Updates 📝

### Communication Layer: MQTT-Based Message Processing Architecture 📱

The communication layer is a key module of the LoRa Smart Agriculture System, implementing efficient message sending and receiving processes based on the MQTT protocol. Its architecture is as follows:
![](doc/images/architecture-diagram-EN.png)

1. **MQTTReq Generation Center**: Generates message objects sent to hardware devices.
2. **MQTT Message Sending Center**: Sends generated messages to the MQTT server.
3. **MQTT Message Receiving Center**: Receives messages returned from hardware devices.
4. **Message Distribution Center**: Distributes received JSON messages to different message parsing units.
5. **Redis Cache Center**: Stores all message data, serving as the message storage center.
6. **Message Parsing Center**: Parses MQTTRes objects and distributes results to corresponding services.
7. **Service Distribution Center**: Passes parsed messages to the dynamic proxy factory to generate required service objects.
8. **Proxy Factory**: Dynamically generates service proxy objects for executing specific database business operations.
9. **Frontend Processing**: Finally returns processing results to the frontend.

**Advantages** 🌟

- **Efficient Communication**: Ensures real-time and reliable message delivery with MQTT-based message sending and receiving mode.
- **Modular Design**: Ensures system flexibility and scalability through layered structure.
- **Data Persistence**: Utilizes Redis to cache message data, improving system fault tolerance.

## License 📜

This project is licensed under the MIT License. 📜
