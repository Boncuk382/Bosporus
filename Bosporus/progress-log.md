# Progress log – Bosporus

This dated log documents the proceess and the key steps, and the progress of the project along with its artifacts.

---

## *10.07.2026* – Phase 1: Sensor node soldering & first readings

### What I did

**Setup HW**
Soldered the two 15-pin header strips onto the Arduino Nano ESP32 (first solder joints
in a while — a bit rough around the edges, but electrically sound). Wired the DHT22 to
the board on a breadboard (VCC → 3V3, DATA → D2, GND → GND). 
 
**Setup development environment**
- Set up PlatformIO in VS Code and 
- Add DHT library
- Add the code to src/main.cpp
- Flashed a first code to read temperature and humidity.

**Artifacts**

![Hardware Setup](images/setup-esp32-with-DHT22.jpeg)

Serial monitor output, confirming the sensor is being read correctly:
![Serial monitor output](images/sensor-data-output.png)

**What went wrong / what I learned**

- First soldering attempt in a long time — needed a refresher on heating the joint (not
  the solder) before feeding solder in.
- Initial header pins were too thick for the breadboard when inserted at an angle;
  fixed by inserting straight down.
- Hit a `'Serial' does not name a type` compile error caused by a mismatched brace, not
  an actual `Serial` problem — a good reminder that C++ error messages sometimes point
  at the *symptom* location, not the *cause* location.

**Result**

✅ End-to-end proof that the sensor node hardware and firmware work: soldering → wiring
→ code → live sensor readings.

---

## *16.07.2026* – Phase 2: Embedded Linux gateway

### What I did
**HW Setup**

**Computer** 
Macbook Air, Apple M3

**Raspberry Pi 4 Model B**
For this project, I wanted to learn embedded Linux in a realistic context — and IoT projects are a natural fit for that, because they almost always call for a gateway in the design. Choosing to build one gave me a concrete reason to get hands-on with embedded Linux, rather than learning it in the abstract.
A gateway earns its place in an IoT architecture for three main reasons:

Centralized connectivity — sensors don't each need their own network hardware; the gateway handles that once, for all of them. The Raspberry Pi covers this well, with WiFi, Ethernet (useful as a stable fallback), and Bluetooth built in.
Centralized security — patching, firewalling, and access control happen on one device instead of being replicated (and potentially neglected) across every sensor node — which is both more secure and cheaper to maintain at scale.
A proper OS for real services — running things like Mosquitto, a database, and Grafana requires a full filesystem, networking stack, and process management — capabilities a microcontroller doesn't have, but a real OS does.

I chose the Raspberry Pi specifically as my learning vehicle for embedded Linux. Compared to alternatives like the Orange Pi or BeagleBone Black, it has the strongest documentation and the largest community — which matters most when you're learning, since it means more tutorials and faster troubleshooting when something goes wrong.

**MicroSD:** Samsung EVO Plus (128 GB, microSDXC, U3, UHS-I)
Because the Pi has no built-in storage, no internal flash, no eMMC. This is the only storage for everything: OS, logs, permanent home of the OS. Every time Pi boots, reads a file or writes a log. 

**Card Reader:** StarTech USB 3.0 card reader with USB-C
I ordered this card reader with USB-C so that I can read the SD card with my MacBook Air, because my MacBook Air does not have a built-in interface capable of reading SD cards. 

**Ethernet adapter** Belkin USB-C auf Gigabit Ethernet Adapter
The Ethernet adapter is the backup for a stable connection if Wifi or mDNS doesnt work. bosporus.local resolves to an IP address via mDNS. If this fails, I need to connect by IP address directly, using a wired connection, which is more predictable. 

**Evidence**

**What went wrong / what I learned**

**Result**
```
