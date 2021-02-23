---
title: Chocolatey
author: Rho
date: 2021-02-23
---

# installing chocolatey

ref: <https://chocolatey.org/courses/installation>

Ensure that you are using an administrative shell, you can also install as a non-admin, check out [Non-Administrative Installation](https://docs.chocolatey.org/en-us/choco/setup#non-administrative-install)

## install with cmd.exe

1. Paste the following text into your shell and press Enter

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

2. Wait a few seconds for the command to complete

3. If you don't see any errors, you are ready to use Chocolatey! Type choco or choco -? now, or see Getting Started for usage instructions

## install with powershell (v3+)

With PowerShell, there is an additional step or two. You must ensure Get-ExecutionPolicy is not Restricted. We suggest using Bypass to bypass the policy to get things installed or AllSigned for quite a bit more security

Run `Get-ExecutionPolicy`. If it returns "Restricted", then run `Set-ExecutionPolicy AllSigned` or `Set-ExecutionPolicy Bypass`

Now run the following command:

```
Set-ExecutionPolicy Bypass -Scope Process -Force; iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
```

# upgrade chocolatey

```
choco upgrade chocolatey
```

# removing chocolatey

- remove folder, say, c:/chocolatey or c:/programdata/chocolatey
- delete environment variables
    * ChocolateyInstall
    * ChocolateyBinRoot
    * ChocolateyToolsLocation
    * PATH (will need updated to remove)

# commands

- list: lists remote or local packages
- search: searches remote or local packages (alias for list)
- info: retrieves package information. Shorthand for choco search pkgname --exact --verbose
- install: installs packages from various sources
- pin: suppress upgrades for a package
- outdated: retrieves packages that are outdated. Similar to upgrade all --noop
- upgrade: upgrades packages from various sources
- uninstall: uninstalls a package
- pack: packages up a nuspec to a compiled nupkg
- push: pushes a compiled nupkg
- new: generates files necessary for a chocolatey package from a template
- sources: view and configure default sources (alias for source)
- source: view and configure default sources
- config: Retrieve and configure config file settings
- feature: view and configure choco features
- features: view and configure choco features (alias for feature)
- setapikey: retrieves or saves an apikey for a particular source (alias for apikey)
- apikey: retrieves or saves an apikey for a particular source
- unpackself: have chocolatey set itself up
- support: provides support information
- download: downloads packages - optionally internalizing all remote resources
- synchronize: synchronizes against system installed software - generates missing packages
- sync: synchronizes against system installed software - generates missing packages
- optimize: optimizes installation, reducing space usage

Please run chocolatey with choco command -help for specific help on each command.

For example, to install git on "C:\git"

```
choco install git --install-args = "'/DIR = C:\git'"
```
