
# SYSIS Changelog

All notable changes to this project will be documented in this file.

This project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [v3.7.7] - 2019-11-28

**Update macOS and RPi board detection**

### Changed

- Add detection for macOS Catalina
- Add detection for new Raspberry Pi boards

## [v3.7.6] - 2018-03-01

**Improve IP Detection**

### Changed

- Reduce timeout when fetching Public IP via dig or curl commands
  - Improves responsiveness for hosts without direct internet connectivity
  - if dig exists - check for external dns access, then retrieve IP with 3s timeout
  - else use curl (if exists) - retrieve IP with 3s timeout

## [v3.7.5] - 2018-02-14

**Minor Adjustments**

### Changed

- adjust README and code cleanup

## [v3.7.4] - 2018-01-26

**Enhancements and Output Adjustments**

### Added

- Enhancements for IP retrieval on Linux with ip command
- enhanced ip output that doesn't include "state UP/DOWN"
- filtered out NIC's with NO-CARRIER or LOOPBACK

### Changed

- fix default color for white backgrounds
- added brackets around IP6 address display
- change spacing of last element for each item
- change color used to display 'Hostname'

## [v3.7.3] - 2018-01-10

**Minor Output Adjustment**

### Changed

- minor fix for CPU speed color boldness setting on Linux

## [v3.7.2] - 2018-01-09

**Enhanced Network Collection and CPU Info**

### Added

- enhances network collection for all scenarios:
  - `ifconfig` and ip on Linux
  - `ifconfig` on macOS
- display CPU version information when available

## [v3.7.1] - 2018-01-08

**Improve Network Data collection on macOS**

### Changed

- Correct awk command used to gather LAN network data on macOS
  - Eliminates non-data gathery due to consecutive single-line entries in ifconfig output
  - Eliminates possible loop issue from ifconfig output

## [v3.7.0] - 2018-01-01

**Add Support for more Network Info and Refined Information Report**

### Added

- Network Info Enhancements
  - Added collection/display of: Adapter Name, IPv6 Address and MAC Address (for active connections)
    - Report only displays data for Active and Non-Virtual Adapters
    - Report only displays defined data (IPv6 not displayed if not assigned or only a local-link address)
  - Gathers network data via `ip` and `ifconfig` based on command availability on host
  - Gathers InternetIP via `dig` and `curl` based on command availability on host

### Changed

- Information Report
  - Reorganized Report to minimize number of lines, improve ability to quickly scan data
  - Incorporate new Network Info without adding additional lines
  - Added "compressed output" mode (accessed by using `-c` parameter)
    - Eliminates whitespace lines in Report (these lines improve scan-ability but use more screen-space)
  - Changed most colors used in the report from **bold** to *normal*
- Enhanced conditional checks when calling non-core commands to eliminates aborts

## [v3.6.3] - 2017-12-23

**Enhanced Lan IP display on Linux hosts with ip command**

### Changed

- LAN IP's displayed in report filtered to only those in the "UP" state

## [v3.6.2] - 2017-12-23

**Enhanced LanIP collection on macOS**

### Fixed

- Eliminated Active IP's from possibly being misidentified as In-Active, and thus not displayed

## [v3.6.1] - 2017-11-02

**Enhanced Public IP Retrieval**

### Added

- Added support for retrieving Internet IP via either `dig` or `curl`

### Changed

- Switched website used to retrieve IP via `curl` as previous site "ipinfo.io" results became inconsistent

## [v3.6.0] - 2017-10-18

**Improvements to Information Report**

### Changed

- Combined CPU Name, Speed & Cores into single line
  - Correct speed displayed on variable speed CPUs
  - Adjust CPU speed to prevent rounding errors
  - Remove CPU Model Number (not consistently displayed on all systems)
- DEVICE line only displayed as needed
- CPU/MEM/DISK items use color to display last parameter

## [v3.5.1] - 2017-10-17

**Enhanced OS Info on Linux**

### Added

- Uses /etc/os-release (if available) which provider richer data

### Changed

- KERNEL version now includes sub-release number (after 3-segment version): "4.10.0-37"
- SYSIS title & version line + empty line below removed from Information Report

## [v3.4.11] - 2017-09-07

**Enhanced LAN IP collection on Linux**

### Added
- Added support for gathering IP4 address using `ip` command if available

## [v3.4.10] - 2017-05-29

**Fix Terminal Type issue on some versions of Debian `tput`**

### Fixed

- Terminal-type "xterm-new" could trigger "unknown" fault in some versions of Debian `tput`

## [v3.4.9] - 2017-04-14

**Refined Information Report**

### Changed

- Combined CPU Speed & Cores into one line

### Removed

- Memory line removed as it was redundant with data in Mem Usage line

## [v3.4.8] - 2017-04-09

**Enhanced Error-Checking and Improved Report**

### Added

- Enhanced conditional checking to prevent run-time errors
- Report section 'Device' only displayed if device values collected

## [v3.4.7] - 2017-03-31

**Streamlining**

### Added

- New functions for variable cleanup and processing
- Eliminate var processing redundancies

## [v3.4.6] - 2017-03-25

**New Installer and Other Enhancements**

### Added

- New installer `install.sh` works for both remote and local installations
- Improvements to memory use calculations on macOS
- Updated Raspberry Pi hardware identification data

[Unreleased]: https://github.com/robertpeteuil/sysis/compare/v3.7.0...develop
[v3.7.7]: https://github.com/robertpeteuil/sysis/compare/v3.7.6...v3.7.7
[v3.7.6]: https://github.com/robertpeteuil/sysis/compare/v3.7.5...v3.7.6
[v3.7.5]: https://github.com/robertpeteuil/sysis/compare/v3.7.4...v3.7.5
[v3.7.4]: https://github.com/robertpeteuil/sysis/compare/v3.7.3...v3.7.4
[v3.7.3]: https://github.com/robertpeteuil/sysis/compare/v3.7.2...v3.7.3
[v3.7.2]: https://github.com/robertpeteuil/sysis/compare/v3.7.1...v3.7.2
[v3.7.1]: https://github.com/robertpeteuil/sysis/compare/v3.7.0...v3.7.1
[v3.7.0]: https://github.com/robertpeteuil/sysis/compare/v3.6.3...v3.7.0
[v3.6.3]: https://github.com/robertpeteuil/sysis/compare/v3.6.2...v3.6.3
[v3.6.2]: https://github.com/robertpeteuil/sysis/compare/v3.6.1...v3.6.2
[v3.6.1]: https://github.com/robertpeteuil/sysis/compare/v3.6.0...v3.6.1
[v3.6.0]: https://github.com/robertpeteuil/sysis/compare/v3.5.1...v3.6.0
[v3.5.1]: https://github.com/robertpeteuil/sysis/compare/v3.4.11...v3.5.1
[v3.4.11]: https://github.com/robertpeteuil/sysis/compare/3.4.10...v3.4.11
[v3.4.10]: https://github.com/robertpeteuil/sysis/compare/v3.4.9...3.4.10
[v3.4.9]: https://github.com/robertpeteuil/sysis/compare/v3.4.8...v3.4.9
[v3.4.8]: https://github.com/robertpeteuil/sysis/compare/v3.4.7...v3.4.8
[v3.4.7]: https://github.com/robertpeteuil/sysis/compare/v3.4.6...v3.4.7
[v3.4.6]: https://github.com/robertpeteuil/sysis/compare/v3.4.0...v3.4.6
