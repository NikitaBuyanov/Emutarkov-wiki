# Obtaining the files

1. create a free github account
2. go to https://github.com/justemutarkov/
3. select the project you want to work on and fork it (see image)
![](https://cdn.discordapp.com/attachments/681164874654417060/682177508128456810/unknown.png)

4. download github desktop and install github desktop
5. login with your github account
6. clone the forked repository

## Server
1. download and install visual studio code
2. download and install node.js (stable release)
3. download resourcehacker (bottom of the project's page, zip file)
4. once you obtained the files, create the <serversource>/dev/bin/ folder and put ResourceHacker.exe in it
5. run install.bat

## Launcher, Emulib
1. download visual studio 2017/2019
2. install with .NET workload and the following components:
    - .NET Framework 2.0
    - .NET Framework 4.6.1


# Starting the development projects

## Server
- run build.bat
- the right executable is EmuTarkov-Server.exe, the other two can be removed.

## Launcher, Emulib
- visual studio 2017/2019 -> menu bar -> build -> rebuild solution
![](https://cdn.discordapp.com/attachments/681164874654417060/682180700614819857/unknown.png)
- launcher: the build exe is located in bin/debug or bin/release
- emulib: the build dll is located in bin/debug or bin/release