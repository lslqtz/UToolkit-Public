# UToolkit

UToolkit is an all-in-one utility app for Apple platforms. It brings together calculation, conversion, developer, diagnostics, and hardware tools in a single native app for iPhone, iPad, Mac Catalyst, and visionOS.

## Features

### Calculation

- Electrical energy: time-of-use electricity pricing, power cost estimation, and appliance usage simulation.
- Financial calculation: loan payment estimation, two-plan interest comparison, and early repayment estimation.
- Network calculation: download time estimation, RTT/BDP calculation, and concurrency/performance estimation.

### Conversion

- Unit conversion: electrical units, storage units, and network units.
- Encoding conversion: Base64 encode/decode, URL encode/decode, Hex encode/decode, and Unicode escape conversion.
- Radix conversion: binary, octal, decimal, and hexadecimal conversion.
- Data type conversion: Float/Int to bytes, byte parsing, Hex view, and endian switching.
- AES encryption/decryption: AES-CBC and AES-GCM, with 128-bit and 256-bit key support.
- Hash calculation: MD5, SHA family hashes, and HMAC signing.

### Developer Tools

- Password tools: random password generation and password strength analysis.
- JSON tools: JSON formatting, minification, and table-style viewing.
- Regex testing: regular expression matching, live highlighting, and capture group inspection.
- Text tools: character and word statistics, case conversion, duplicate removal, and text processing.
- IP calculation: subnet calculation, mask calculation, and usable address range calculation.

### Utilities

- System diagnostics: basic device information, memory details, battery status, network information, and sensor information.
- Timestamp tools: Unix timestamp to date, date to timestamp, and time difference calculation.
- QR code tools: QR code generation and QR code scanning.
- Port scanner: TCP port scanning for user-specified hosts.
- LAN scanner: online host discovery, device name identification, and IP address listing.
- Document conversion: Markdown to HTML/PDF.
- Color tools: HEX/RGB/HSL conversion, palette browsing, and color value copying.
- Network diagnostics: Ping latency testing and Traceroute route tracing.

### USB Serial Tools

On macOS through Mac Catalyst, UToolkit includes a USB serial debugging tool for embedded development and hardware diagnostics.

Planned and supported serial workflows include:

- Detecting common USB-to-serial bridge chips.
- Configuring baud rate, data bits, stop bits, and parity.
- Sending and receiving serial data in text or Hex mode.
- Supporting common adapters such as WCH CH34x, Silicon Labs CP210x, FTDI USB-to-Serial, and Prolific PL2303.
- Using an existing macOS or vendor serial driver when one is available.
- Providing DriverKit-based support for selected USB-to-serial adapters when no suitable driver is available.

## DriverKit Purpose

UToolkit may include a DriverKit driver extension for USB serial devices. The driver extension is intended to match supported USB-to-serial adapters by USB vendor/product identifiers, configure serial communication parameters, and exchange serial data only after explicit user action.

Requested DriverKit capabilities are limited to USB serial adapter support:

- DriverKit Serial
- DriverKit USB Transport
- UserClient Access, when the main app needs to communicate directly with the DriverKit extension
- System Extension installation, when the app installs or manages the DriverKit extension

Bundle identifiers:

```text
Main app: com.bowen.utoolkit
Planned DriverKit extension: com.bowen.utoolkit.serialdriver
```

## Privacy

UToolkit does not connect to or upload user content to our own servers.

Some tools may communicate with user-selected local or remote targets in order to perform the requested operation. For example, port scanning, LAN scanning, Ping, Traceroute, QR code scanning, document export, and serial communication operate only when initiated by the user.

Serial data is processed locally between the user's device and the connected hardware. UToolkit does not upload serial logs or transmitted serial data to our servers.

Apple may collect diagnostic information depending on the user's Apple system settings and App Store/TestFlight diagnostics preferences. This may include crash logs, performance data, telemetry, and other diagnostic information used to improve app quality. We may review aggregated or Apple-provided diagnostic reports for technical improvement. Such data is generally not associated with the user and is discarded when no longer needed for debugging or product improvement.

## Platform

- iOS
- iPadOS
- macOS through Mac Catalyst
- visionOS

Some hardware-related features may be available only on platforms that provide the required system APIs and hardware access.

## Support

Please use GitHub Issues for bug reports, support requests, and feature suggestions.
