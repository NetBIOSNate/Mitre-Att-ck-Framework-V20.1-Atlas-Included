# DC0016 - Module Load

[Mobile](../../README.md) / [Data Components](README.md)

When a process or program dynamically attaches a shared library, module, or plugin into its memory space. This action is typically performed to extend the functionality of an application, access shared system resources, or interact with kernel-mode components.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0016)

## Log sources and channels

- **android:logcat** — DexClassLoader/PathClassLoader load attempt from non-standard path or recently created file
- **android:logcat** — Short burst of file I/O followed by JNI/dlopen of a newly created .so
- **android:logcat** — DexClassLoader/PathClassLoader loading from app-writable path OR reflective defineClass on byte[] payload
- **android:logcat** — DexClassLoader|PathClassLoader load from app-writable path OR dlopen of a freshly created .so
- **auditd:file-events** — open of suspicious .so from non-standard paths
- **auditd:MMAP** — load: Loading of libzip.so, libz.so, or libbz2.so by processes not normally associated with archiving
- **auditd:SYSCALL** — openat/read/mmap: Open/mmap .so files from non-standard paths
- **auditd:SYSCALL** — LD_PRELOAD Logging
- **auditd:SYSCALL** — mmap
- **auditd:SYSCALL** — dmesg
- **auditd:SYSCALL** — module load or memory map path
- **esxi:vmkernel** — unexpected module load
- **esxi:vmkernel** — module load
- **ETW:LoadImage** — provider: ETW LoadImage events for images from user-writable/UNC paths
- **etw:Microsoft-Windows-Kernel-ImageLoad** — provider: Unsigned/user-writable image loads into msbuild.exe
- **iOS:unifiedlog** — dyld: dlopen/dyld_cache load from non-standard app-writable path
- **iOS:unifiedlog** — dlopen/image load from app-writable path (tmp, Caches) outside bundled resources
- **linux:osquery** — select: Open files path LIKE '/tmp/%.so' OR '/dev/shm/%.so'
- **linux:osquery** — Dynamic Linking State
- **linux:osquery** — Process linked with libcrypto.so making external connections
- **linux:osquery** — Processes linked with libssl/libcrypto performing network activity
- **linux:syslog** — kmod
- **linux:Sysmon** — EventCode=7
- **m365:unified** — Non-standard Office startup component detected (e.g., unexpected DLL path)
- **macos:endpointsecurity** — ES_EVENT_TYPE_NOTIFY_KEXTLOAD
- **macos:osquery** — select: path LIKE '%/Library/%/*.dylib' OR '/tmp/*.dylib'
- **macos:syslog** — DYLD_INSERT_LIBRARIES anomalies
- **macos:unifiedlog** — dyld/unified log entries indicating image load from non-system paths
- **macos:unifiedlog** — dynamic loading of sleep-related functions or sandbox detection libraries
- **macos:unifiedlog** — DYLD event subsystem
- **macos:unifiedlog** — process execution events with dylib load activity
- **macos:unifiedlog** — Process memory maps new dylib (dylib_load event)
- **macos:unifiedlog** — Dylib loaded from abnormal location
- **macos:unifiedlog** — Loading of libz.dylib, libarchive.dylib by non-standard applications
- **macos:unifiedlog** — suspicious dlopen/dlsym usage in non-development processes
- **macos:unifiedlog** — delay/sleep library usage in user context
- **macos:unifiedlog** — subsystem=com.apple.kextd
- **macos:unifiedlog** — loading of unexpected dylibs compared to historical baselines
- **macos:unifiedlog** — launch and dylib load
- **Module** — None
- **snmp:status** — Status change in cryptographic hardware modules (enabled -> disabled)
- **WinEventLog:Application** — CLR Assembly creation, loading, or modification logs via MSSQL CLR integration
- **WinEventLog:Security** — EventCode=3033
- **WinEventLog:Security** — EventCode=3063
- **WinEventLog:Sysmon** — EventCode=7; scripting-engine module loads when useful 
- **WinEventLog:Sysmon** — EventCode=7; System.Management.Automation or unusual PowerShell-related modules
- **WinEventLog:Sysmon** — EventCode=7
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: DexClassLoader() or dlopen() called with path argument matching file written in preceding $DecryptExecWindow$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: DexClassLoader() or dlopen() on path written within $StegoExecWindow$ of media download event — download-write-load chain confirms steganographic payload delivery
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: DexClassLoader() called at runtime with path NOT matching any file in original APK manifest within $PackerExecWindow$ of app launch
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: DexClassLoader() or System.load() or WebView.loadUrl(javascript:) called with content_source='network_download' within $CodeDownloadWindow$ of download event
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): syscall=init_module/finit_module; kernel module loaded from a path or hash not in the authorized ICS host module baseline
- **WinEventLog:Sysmon** — EventCode=7 of Industrial Control Systems (ICS) vendor communication Dynamic Link Library (DLL) with hash not in signed baseline
- **WinEventLog:Sysmon** — EventCode=7 where an ICS/vendor DLL is loaded by an image outside the authorized ICS application baseline
- **WinEventLog:Sysmon** — EventCode=7 of GDI32.dll/User32.dll by process not in authorized screen capture tools on Human-Machine Interface (HMI)-classified host

## Analytics using this component

- [AN1677 - Analytic 1677](../Analytics/AN1677.md)
- [AN1722 - Analytic 1722](../Analytics/AN1722.md)
- [AN1780 - Analytic 1780](../Analytics/AN1780.md)
- [AN1851 - Analytic 1851](../Analytics/AN1851.md)
