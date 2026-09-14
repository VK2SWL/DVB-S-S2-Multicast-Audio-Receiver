# DVB-S-S2-Multicast-Audio-Receiver

A Windows receiver for DVB satellite multicast audio carried inside MPEG transport streams. It can tune supported Windows BDA satellite devices directly through TSDuck, decode DSM-CC/MPE → IPv4/UDP/RTP audio, discover SAP/SDP services, display RCS/UECP/RDS metadata, play the selected stream, open it in normal VLC, record audio, and run a deep MPE scanner.

<img width="2555" height="1368" alt="image" src="https://github.com/user-attachments/assets/2f990504-5f0b-461d-bd2b-bc574ea09f20" />

# Fresh install — do this first
Extract the complete ZIP to a normal writable folder.
Run INSTALL-DEPENDENCIES.cmd once on a fresh installation.
Launch dvb_multicast_gui.py to start DVB-S/S2 Multicast Audio Receiver.
START-RECEIVER.cmd is included only as an optional convenience launcher.
The dependency installer selects a compatible 64-bit Python 3.8–3.14 environment and installs the required Python packages.

# Quick start — Direct Windows BDA tuner
Launch dvb_multicast_gui.py.
Choose Direct Windows BDA satellite tuner.
Click Detect Tuners and choose the required tuner.
Enter frequency, symbol rate, polarisation, delivery system, modulation, LNB values and the initial MPE PID.
Press Start.
Select a discovered audio feed.
Use the built-in Play button, or click Open in VLC to launch the current decoded stream in the normal VLC application.
Optional controls let you choose an audio output, record MP3/WAV/M4A, view metadata and UECP/RDS, capture the raw selected PID, or run Deep Scan.
The Direct BDA path uses the Windows BDA driver and TSDuck for tuner control. VLC is used only for audio playback/recording.
Open in VLC
The Open in VLC button is beside the playback/volume controls in the Now Playing panel. It opens the currently selected decoded local audio stream in the normal VLC desktop application. The built-in player remains available separately.

# Supported source modes
Direct Windows BDA satellite tuner — preferred for a compatible Windows BDA tuner.
Enigma2 receiver — existing SSH/dvbsnoop source path.
EBS Pro / external raw TS — receives a full raw MPEG transport stream over UDP.
Audio and metadata support
AAC/ADTS and HE-AAC LATM/LOAS playback routing.
RTP audio discovery from DVB MPE.
SAP/SDP service discovery, including split-PID announcements.
RCS metadata and UECP/RDS display where present.
MP3, WAV and M4A recording of the selected decoded feed.
Selectable Windows audio output when compatible libVLC is available.

# Known Supported DVB-S/S2 PC Tuners
TBS 5927 (Tested)

TBS 6925 (Tested)

TBS 5930 Lite (Tested)

TBS 6983 (Works by tuning with EBS Pro)

# Known Unsupported DVB-S/S2 PC Tuners


# Deep Scan
The built-in Deep Scanner can inspect all PIDs for DSM-CC/MPE, reconstruct IPv4/UDP, identify RTP/AAC and SAP/SDP traffic, and correlate multicast audio services even when normal DVB service signalling is incomplete.
See docs\MPE-DEEP-SCANNER.md for details.
TSDuck
The receiver can use a normal TSDuck installation from PATH or offer to download the official portable Windows x64 package into tools\tsduck on first Direct BDA use.
VLC
The application checks common 64-bit and 32-bit VLC installation locations, registry entries, PATH, user-local locations and an optional portable vlc folder beside the application.
For Open in VLC, any detected normal VLC executable can be used. For embedded output-device selection, the VLC/libVLC architecture must be compatible with the Python process.

# Diagnostics
Open the Diagnostics tab or click Open Log. Direct tuner messages are prefixed with [BDA] / [BDA/TSDuck], recording messages with [REC], and audio routing messages with [AUDIO].
START-DIAGNOSTIC.cmd is included for Python/PySide6 startup troubleshooting.

# Notes for Release V1
Release V1 is the cleaned public release based on the proven standalone BDA, SAP/SDP, LATM/LOAS, recording, output-routing and Deep Scan code. This release focuses on naming, packaging, documentation and usability. TBS 5930 Lite / driver-reported 5931 compatibility investigation is intentionally deferred to the next development version.

# Third-party software
TSDuck is distributed under the BSD 2-Clause license; its notice is included under THIRD-PARTY-LICENSES. VLC, Python, Qt/PySide6, Paramiko and tuner drivers retain their respective licenses.

# Help
For Help and feedback please email me at VK3SWL@Hotmail.com
