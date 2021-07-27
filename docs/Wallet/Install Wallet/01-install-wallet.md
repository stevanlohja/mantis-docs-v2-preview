# Download & Install

## Prerequisites

See [system requirements](/Wallet/Install%20Wallet/00-system-requirements%20copy/).

This section outlines how to install the Mantis wallet on your Mac, Linux, or Windows machine. If you want the client, follow the [client installation instructions](/Client/start-mantis/).

## MacOS

To install Mantis wallet, follow these steps:

* Choose and download the Apple Mac installer from the [wallet releases page](https://github.com/input-output-hk/mantis-wallet/releases/latest). 
The Apple installer is the one with the .dmg extension.
Note the checksum.
```
Mantis-Wallet-<version>.dmg
```
> Remember to run checksum verification on your downloads. Refer to [this section](/how-tos/how-check-hash-mac) for instructions.

* Open (mount) the .dmg file and proceed with a standard Mac install. 

```
mv Mantis-Wallet-3.1.0.AppImage /home/<user>/bin/
cd /home/<user>/bin/
```
After mounting the dmg file, drag the 'Mantis-Wallet' icon to the 'Applications' shortcut in the same window. You can unmount it later.
![Mac Install](../images/3c-Install-Mac.png)
>We recommend placing the Mantis folder in the default folders provided during install.

* Now, you can run the wallet by double-clicking the file or running it through your Desktop environment.

During startup, Mantis wallet allows you to choose the network. The network is the blockchain to synchronize. Here is the splash screen:
![splash screen](../images/5-splash-screen.png)

For information on the available networks, see [this page](/learn/mantis-client-wallet)

As soon as it starts, Mantis begins synchronizing with the chosen network. In the image, Mantis is started in the Sagano Testnet.
![setup 1](../images/4-Setup-1.png)

For the next steps in the story, go to the **Learn** or **How to** sections.

### Update

To update the Mantis wallet, replace the binary with the newer version and use the new file instead of the older one.

```
mv Mantis-Wallet-<newer-version>.AppImage /home/<user>/bin/
```

## Linux

To install Mantis wallet, follow these steps:

* Download the wallet binary from the [wallet releases page](https://github.com/input-output-hk/mantis-wallet/releases/latest).
Choose and download the Linux installer from the wallet releases page. The Linux installer is the one with the AppImage extension.

```
Mantis-Wallet-<version>.AppImage
```
* Note the checksum.
> Remember to run checksum verification on your downloads. Refer to [this section](/how-tos/how-check-hash-linux) for instructions.

* For more information, see [where to place the AppImage file](https://docs.appimage.org/user-guide/faq.html#question-where-do-i-store-my-appimages). 

* Mark the Appimage file executable:
![Linux screenshot](../images/2c-Linux-Mark-Executable.png)
* Now, you can run the wallet by double-clicking the AppImage file or running it through your Desktop environment.

> On recent Debian distributions, every time you run the AppImage file you need to add the no-sandbox switch like this: `./mantis.appimage --no-sandbox`  
For more information, see [this Reddit discussion](https://www.reddit.com/r/debian/comments/hkyeft/unable_to_run_appimage_applications_without/) 

During startup, Mantis wallet allows you to choose the network. The network is the blockchain to synchronize. Here is the splash screen:
![splash screen](../images/5-splash-screen.png)

For information on the available networks, see [this page](/learn/mantis-client-wallet)

As soon as it starts, Mantis begins synchronizing with the chosen network. In the image, Mantis is started in the Sagano Testnet.
![setup 1](../images/4-Setup-1.png)

For the next steps in the story, go to the **Learn** or **How to** sections.

### Update

To update the Mantis wallet, replace the binary with the newer version and use the new file instead of the older one.
```
mv Mantis-Wallet-<newer-version>.AppImage /home/<user>/bin/
```

## Windows

To install Mantis wallet, follow these steps:

* Choose and download the Windows 64 bit installer from the [wallet release page](https://github.com/input-output-hk/mantis-wallet/releases/latest). the Windows installer is the one with the .exe extension.
* Note the checksum.
> Remember to run checksum verification on your downloads. Refer to [this section](/how-tos/how-check-hash-windows) for instructions.

* Execute the binary file to run the installer. It is a standard Windows installer.
![Installer Starting](../images/3-Install-Complete.png)

> The default installation folder is Program Files/Mantis-Wallet. We recommend placing the Mantis files there.


* Now, you can run the wallet by double-clicking its executable or running it through your desktop environment. The installation process adds a shortcut to your start menu.

During startup, Mantis wallet allows you to choose the network. The network is the blockchain to synchronize. Here is the splash screen:
![splash screen](../images/5-splash-screen.png)

For information on the available networks, see [this page](/learn/mantis-client-wallet)

As soon as it starts, Mantis begins synchronizing with the chosen network. In the image, Mantis is using the Sagano Testnet.
![setup 1](../images/4-Setup-1.png)

For the next steps in the story, go to the **Learn** or **How to** sections.


### Update

To update the Mantis wallet, download a new installer and repeat the installation process.
