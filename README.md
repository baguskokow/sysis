# sysis
### Display Key System Information with this lightweight Cross-Platform Utility
[![Code Climate](https://codeclimate.com/github/robertpeteuil/sysis/badges/gpa.svg)](https://codeclimate.com/github/robertpeteuil/sysis)
[![GitHub issues](https://img.shields.io/github/issues/robertpeteuil/sysis.svg)](https://github.com/robertpeteuil/sysis)
[![GitHub release](https://img.shields.io/github/release/robertpeteuil/sysis.svg?colorB=2067b8)](https://github.com/robertpeteuil/sysis)
[![lang](https://img.shields.io/badge/language-bash-89e051.svg?style=flat-square)]()
[![license](https://img.shields.io/github/license/robertpeteuil/sysis.svg?colorB=2067b8)](https://github.com/robertpeteuil/sysis)

---

**Ideal for sysadmins, developers and system builders who connect to dozens of systems daily.**  SYSIS provides a quick display of key system information without the need to run multiple different utilities.  It also avoids the bloat that is common in other System Information Utilities.

### Screenshot of sysis output: 
![](https://cloud.githubusercontent.com/assets/1554603/24317998/d63074e8-10bb-11e7-82d2-3e82c1b4755a.png)

### Supported Platforms

  - Linux
  - macOS / OS X
  - Raspberry PI (Linux)
  - Windows 10 with "Bash on Windows"  
    
### Execution

This is a command is executed simply with `sysis`

> Optional parameters:
> -  `-h` - 'help'
> -  `-n` - 'network only mode'
> -  `-d` - 'debug' - displays values by method obtained
> -  `-V` - 'version info'
> -  `--help` - 'detailed help info' - displays additional help including exit status information

### Installation:

Can be install with curl

```shell
bash -c "`curl -s -L https://raw.github.com/robertpeteuil/sysis/master/install.sh`"
```


If the repo has been downloaded locally, cd into the directory and run install.sh

```shell
cd sysis
./install.sh
```
