---
layout: post
title: Powershell-Core and Posh-git
execerpt: "Community"
categories: [Posts]
tags: [Post]
comments: true
---

## Powershell Core

### What is Powershell core ?

So a bit of history, Microsoft Announced The General availability of Powershell Core on January 10, 2018 And PowerShell Core is a new version of PowerShell,
an open-source command-line shell and scripting language that ships with Microsoft Windows.

Microsoft sees PowerShell Core as an evolution of PowerShell. The former is available as a cross-platform application, the latter only for Windows.
Means that script that you write will run on any supported operating system such as Windows,Mac OS X, Linux Devices and even experemintal versions of ARM devices.

### Wait,So What's the difference between Powershell and Powershell Core ?

Great Question, Powershell is build using .Net Framework and .Net Standard and Powershell core is build using .Net Core and .Net Standard which mean
Powershell is pretty more powerful than Powershell core

on the other hand you can use powershell core from anywhere (Linux,Mac OS X,Windows) and
Microsoft works actively on PowerShell Core. PowerShell, on the other hand, is in a state that can best be compared to extended support for Windows versions.
Microsoft has no plans to add features to PowerShell, but it will release critical bug fixes and security updates.

|                            | PowerShell                       | Powershell Core                          |
| -------------------------- | -------------------------------- | ---------------------------------------- |
| Versions                   | 1.0 to 5.1                       | 6.0                                      |
| Platforms                  | Windows only (client and server) | Windows, Mac OS, Linux                   |
| Dependency                 | .Net Framework                   | .Net Core                                |
| Usage                      | Relies on .Net Framework runtime | Relies on .Net Core runtime              |
| Launched as                | powershell.exe                   | pwsh.exe (Windows), pwsh (Mac and Linux) |
| \$PSVersionTable.PSEdition | Set to Desktop                   | Set to Core                              |
| Update policy              | critical bug fixes only          | all updates (features, bugs)             |

### How To Install it

- Windows

1. Get the package from [Powershell Github](https://github.com/powershell/powershell){: target="\_blank"}

2. start .msi and it will open installer windows

3. <img src ="../../img/Posh_git_and_pwsh/Powershell-core-msi.png" style="width: 640px;height: auto;">
   - Add PowerShell to Path Environment mean that its automatically will add the path to the environment variable so you can open it from any directory in cmd/powershell

   - Register Windows Event Logging manifest

   - Enable Powershell Remoting mean you can remote another device powershell using your device powershell if you wanted to deploy something you dont have
     to come to your server

   - Add 'Open here' context menus to explorer mean when you right-click at some folder in windows explorer there will be an option 'Open with Powershell core"

4. Wait until the installation complete

5. You can open powershell core from cmd by typing

   ```sh
   pwsh
   ```

   or press Windows+r then type

   ```
   pwsh
   ```

- Linux

  - Ubuntu 14.04/16.04/18.04

    1. Download The Microsoft repository GPG keys


        ```sh
        $ wget -q https://packages.microsoft.com/config/ubuntu/<version>/packages-microsoft-prod.deb
        # If its 18.04  https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
        ```

    2. Register the Microsoft repository GPG keys


        ```sh
        $ sudo dpkg -i packages-microsoft-prod.deb
        ```

    3.  Update the list of the packages


        ```sh
        $ sudo apt-get update
        ```

    4. Install PowerShell


        ```sh
        $ sudo apt-get install powershell
        ```


    5. Start powershell


        ```sh
        $ pwsh
        ```

    + Uninstall Powershell

        ```sh
        $ sudo apt-get remove powershell
        ```

- MacOS

  1. Install Powershell


        ```sh
        $ brew cask install powershell
        ```


  2. start powershell


        ```sh
        $ pwsh
        ```


  3. When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell


        ```sh
        $ brew update
        $ brew cask upgrade powershell
        ```


    + Uninstall Powershell core from MacOS 


        ```sh
        $ brew cask uninstall powershell
        ```


for more information about [Powershell](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6){:target ="\_blank"}

Contribute to [Powershell](https://github.com/powershell/powershell){: target="\_blank"}

### What is Posh-git ?

Posh git is an Open Powershell module that integrates Git and powershell by providing Git status information that can be displayed in PowerShell...<b>neat</b>

<img src ="../../img/Posh_git_and_pwsh/posh-git.png">

### How Can i Install it?

1. Open cmd/powershell on adminstrator then check the execution policy


    ```sh
    $ Get-ExecutionPolicy
    ```


    + if its ```Restricted``` change your execution policy by 


        ```sh
        $ Set-ExecutionPolicy RemoteSigned
        ```
    

    > Execution policy is the setting for running script that were not originated from the system which mean we cant run an external script

    > for more information about [Execution Policy](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-6){: target="_blank"}


2. Download The package


    ```sh
    $ git clone https://github.com/dahlbyk/posh-git
    ```


3. go to the posh-git directory and run the installer

    ```sh
    $ cd posh-git/
    $ ./install.ps1
    ```

for more information about [Posh-git](https://github.com/dahlbyk/posh-git){: target="_blank"} 