# Wine-for-ChromeOS
Wine (originally an acronym for "Wine Is Not an Emulator") is a compatibility layer capable of running Windows applications on Linux, macOS, &amp; BSD. You can now install it on a Chromebook using these commands (or by executing the .bash file) and run Windows apps on your Chromebook. Note that this is not official. 

This will only work on Chromebooks with an Intel or AMD CPU. You also need to have Linux enabled on your Chromebook.
## How to enable Linux on a Chromebook
1. Open settings
2. Navigate to "Linux (Beta)" or "Developers" (this depends on your ChromeOS version, the name will change to "Linux development environment (Beta)" once you navigate to it".
3. Click "Turn on"
4. A setup guide will appear. It will ask you how much storage you want to give the Linux virtual machine, we recommend 10GB as WineHQ is over 1GB (7GB at minimum, this will give you a little space for more apps later).

Linux will now install. It can take a few minutes. When it's complete, the terminal will appear. You then have to run `sudo apt update`.

## Download Wine using the .bash file
This makes the process automatic, all while installing the required services for WineHQ (stable). Download the file first, then run these commands:
```
ls <where the file is>
chmod +x WineHQ_6.0_for_ChromeOS.bash
./WineHQ_6.0_for_ChromeOS.bash
```
1. You will need to answer with "Y" when `--install-recommends winehq-stable` is ran.
2. Wine will prompt you to install more packages such as the Microsoft .NET framework. This is required in order for Wine to work, you can just press "Install" on the prompts that appear (graphical).

## Download using terminal commands
All these commands are already in *WineHQ_6.0_for_ChromeOS.bash*, though you can paste the commands yourself. Before you do this, you might want to run `sudo apt update` if you haven't run it in some time. Otherwise Wine might not work properly.
```
sudo dpkg --add-architecture i386 && wget -nc https://dl.winehq.org/wine-builds/winehq.key && sudo apt-key add winehq.key && echo "deb https://dl.winehq.org/wine-builds/debian/ buster main" | sudo tee /etc/apt/sources.list.d/wine.list && echo "deb https://download.opensuse.org/repositories/Emulators:/Wine:/Debian/Debian_10 ./" | sudo tee /etc/apt/sources.list.d/winehq.list && sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys DFA175A75104960E && sudo apt update && sudo apt install --install-recommends winehq-stable && winecfg
```

## Additional resources
- To learn more about Wine, visit winehq.org
- The original source is at [linuxmadesimple.info](https://www.linuxmadesimple.info/2021/01/how-to-use-and-install-wine-60-on.html), however is simplified here.
