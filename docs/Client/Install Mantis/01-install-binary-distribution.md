# Install Binary Distribution

To install Mantis via binary distribution, follow these steps:

## Prerequisites

See [system requirements](/Client/Install/System%20Requirements/).

## MacOS / Linux

* Download the client binary zip archive from the [Mantis Client page](https://github.com/input-output-hk/mantis/releases/latest).
* Note the checksum.
* Run checksum verification
!!! Note 
    Remember to run checksum verification on your downloads. Refer to these instructions for [Linux](/how-tos/how-check-hash-linux) or [Mac](/how-tos/how-check-hash-mac).
* Move the zip file to your preferred folder and unzip the client archive file. Finally, remove the zip file.

```
mv mantis-3.2.1.zip/home/<user>/bin/
cd /home/<user>/bin/
unzip mantis-3.2.1.zip
rm mantis-3.2.1.zip
```

* (Optional) Rename your Mantis bin folder for future updates.

```
mv /home/<user>/bin/mantis-3.2.1/home/<user>/bin/mantis
```

!!! Note
    Default folders for applications are `/home/<user>/Applications` and `/home/<user>/bin`, or `/usr/local/bin`. We recommend placing the Mantis folder in there.


* Now, you can run the client from its install folder.

```
bin/mantis-launcher <network-name>
```

This command runs the client in the foreground with settings defined in the `<network-name>.conf` file in the `conf` folder under the Mantis base folder.

The client synchronizes with your chosen network as soon as it starts. The synchronization process can take several hours, depending on the network selected.

For information on the available networks, see [the client and wallet page](/learn/mantis-client-wallet)

### PATH
* (Optional, but recommended) Add the binary to your PATH. Add the following line to your `.profile`/`.bashrc`/`.zshrc` (or equivalent). Source the profile file.

```
export PATH=$PATH:~/bin/mantis-3.1.0/bin
source ~/.profile
```

### Update

To update the Mantis client, replace the Mantis folder with the newer version.

```
mv mantis-<newer-version>.zip /home/<user>/bin/
unzip mantis-<newer-version>.zip /home/<user>/bin/mantis
```

## Windows

* Download the client binary zip archive to your preferred folder from the [Mantis Client page](https://github.com/input-output-hk/mantis/releases/latest).
* Note the checksum.
   
!!! Note 
    Remember to run checksum verification on your downloads. Refer to [this section](/how-tos/how-check-hash-windows) for instructions.

* (Optional) Rename your Mantis bin folder for ease of future updates.
* Now, you can run the client from its install folder, as follows:

```
cd <Mantis-Folder>/bin
mantis-launcher.bat <Network-Name>
```

This command runs the client in the foreground with settings as defined in the `<Network-Name>.conf` file in the `conf` folder.

The client synchronizes with your chosen network as soon as it starts. The synchronization process can take several hours, depending on the network selected.

For information on the available networks, see [this page](/learn/mantis-client-wallet)

### Update

To update the Mantis client, download a new installer and repeat the installation process.