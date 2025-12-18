# Windows 11 Performance Optimization

> Deep optimization guide for AMD Ryzen 9 9950X3D + NVIDIA RTX 5070 Ti

## System Specs Target

- **CPU**: AMD Ryzen 9 9950X3D (16-core, 32-thread, 3D V-Cache)
- **GPU**: NVIDIA GeForce RTX 5070 Ti
- **RAM**: 64GB DDR5
- **OS**: Windows 11 Pro Build 26200+

---

## BIOS Optimization (Ryzen 9950X3D)

### Essential Settings

1. **Update BIOS** - Non-negotiable for AGESA updates
2. **Enable E.X.P.O** - Extended Memory Profile for DDR5
3. **Enable PBO2** - Precision Boost Overdrive 2

### PBO2 Configuration

```
PBO Limits: Manual (use defaults, not manufacturer limits)
Frequency Override: +200 MHz
Curve Optimizer: -20 to -30 (start -30, reduce if unstable)
Scalar: 2x (not 10x for daily use)
```

### Memory Settings

```
DDR5 Frequency: 6000-6400 MHz (sweet spot)
Infinity Fabric: 1800-2000 MHz (auto or 1:1 sync)
Timings: CL30 or lower
```

### V-Cache Specific

- CCD with 3D V-Cache: Higher negative CO offset
- Non-X3D CCD: Less aggressive tuning
- For pure gaming: Consider disabling CCD1, keep SMT enabled

---

## Registry Optimizations

### Network Latency (Nagle's Algorithm)

```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\{INTERFACE_GUID}]
"TcpAckFrequency"=dword:00000001
"TCPNoDelay"=dword:00000001
```

### Memory Management

```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management]
"ClearPageFileAtShutdown"=dword:00000000
"DisablePagingExecutive"=dword:00000001
"LargeSystemCache"=dword:00000000
```

### SSD Optimization

```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters]
"EnableSuperfetch"=dword:00000000
"EnablePrefetcher"=dword:00000000
```

### NTFS Performance

```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem]
"NtfsDisable8dot3NameCreation"=dword:00000001
"NtfsDisableLastAccessUpdate"=dword:00000001
```

### Gaming Optimization

```reg
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile]
"SystemResponsiveness"=dword:00000000
"NetworkThrottlingIndex"=dword:ffffffff

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games]
"GPU Priority"=dword:00000008
"Priority"=dword:00000006
"Scheduling Category"="High"
"SFIO Priority"="High"
```

### GPU Hardware Scheduling

```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\GraphicsDrivers]
"HwSchMode"=dword:00000002
```

### Power Throttling Disable

```reg
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerThrottling]
"PowerThrottlingOff"=dword:00000001
```

### UI Performance

```reg
[HKEY_CURRENT_USER\Control Panel\Desktop]
"MenuShowDelay"="0"
"WaitToKillAppTimeout"="2000"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control]
"WaitToKillServiceTimeout"="2000"

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Themes\Personalize]
"EnableTransparency"=dword:00000000
```

### Telemetry Disable

```reg
[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\DataCollection]
"AllowTelemetry"=dword:00000000
```

### Game DVR Disable

```reg
[HKEY_CURRENT_USER\System\GameConfigStore]
"GameDVR_Enabled"=dword:00000000
```

---

## PowerShell Optimizations

### Disable Core Parking

```powershell
powercfg -setacvalueindex scheme_current sub_processor CPMINCORES 100
powercfg -setactive scheme_current
```

### Enable Ultimate Performance

```powershell
powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61
```

### Disable HPET (Lower Latency)

```cmd
bcdedit /set useplatformclock false
bcdedit /set disabledynamictick yes
```

### Clean Caches

```powershell
# Temp files
Remove-Item -Path "$env:TEMP\*" -Recurse -Force -ErrorAction SilentlyContinue
Remove-Item -Path "C:\Windows\Temp\*" -Recurse -Force -ErrorAction SilentlyContinue

# Windows Update cache
Stop-Service wuauserv -Force
Remove-Item -Path "C:\Windows\SoftwareDistribution\Download\*" -Recurse -Force
Start-Service wuauserv

# DNS cache
Clear-DnsClientCache

# Thumbnail cache
Remove-Item -Path "$env:LOCALAPPDATA\Microsoft\Windows\Explorer\thumbcache_*.db" -Force
```

---

## NVIDIA RTX 5070 Ti Settings

### NVIDIA Control Panel

```
Power Management: Prefer Maximum Performance
Texture Filtering Quality: High Performance
Threaded Optimization: On
Low Latency Mode: Ultra (for competitive)
G-SYNC: On (if supported)
```

### Driver Settings

- Use Studio Drivers for content creation
- Use Game Ready Drivers for gaming
- Disable GeForce Experience overlay if not needed

---

## Services to Disable

```powershell
# Telemetry
Set-Service DiagTrack -StartupType Disabled
Set-Service dmwappushservice -StartupType Disabled

# Search (if not used)
Set-Service WSearch -StartupType Manual

# Fax
Set-Service Fax -StartupType Disabled
```

---

## Resources

- [kubaam/Windows-11-Fix-Tweaks](https://github.com/kubaam/Windows-11-Fix-Tweaks)
- [Windows Insider Build Notes](https://blogs.windows.com/windows-insider/)
- [AMD Ryzen Tuning Guides](https://skatterbencher.com)
- [Tom's Hardware Forums](https://forums.tomshardware.com)
