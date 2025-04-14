# WSL Help Commands

This commands will help you to control and confiuger the WSL.

Use this command to see the current instants.

```bash

wsl  -l  -v

```
Use this command to see the available distro that you can install.

```bash

wsl  -l  -o

```

## Install WSL

Install common WSL distribution.

```bash

wsl  --install

```
Install WSL distro as you like by replacing the distro name with `<distro>` in command.

```bash

wsl  --install  -d <distro>

```

>  **Note:** When you want to install multiple distributions, I recommend you to use the Microsoft Store.

## Run Multiple Instants Using Export & Import

### Export

Using this command, you can backup the already installed distro in WSL. you can export the instant as `.tar` file.

Replace the `<Distro Name>` with actual distro name (use `wsl -l -v` to see all actual names) and replace the `<Distro Backup File Path>`⁣ with actual file path to the backup `.tar` file.

```bash

wsl  --export <Distro  Name> <Distro  Backup  File  Path>

```
Example:

```bash

wsl  --export  ex-distro  c:\path\to\backup-folder\ex-distro-backup.tar

```

### import

After exporting the instant, you can import the instant again as new instant in the WSL.

Replace the `<New Distro Name>` as you like (this is a new name for the instant). Replace the `<Distro Install Path>` with the path you want to store the instant files. Replace the `<Distro Backup File Location>` with the actual location of the backup `.tar` file of the distro.

```bash

wsl  --import <New  Distro  Name> <Distro  Install  Path> <Distro  Backup  File  Location>

```
Example:

```bash

wsl  --import  ex-new-distro  c:\path\to\wsl-install-folder  c:\path\to\backup-folder\ex-distro-backup.tar

```

## Windows Port Forwarding - Can access WSL from any device.

Recommended to use Windows PowerShell run as administrator.

**Show available port forwarding.**
```powershell
netsh interface portproxy show v4tov4
```
**Set new port forwarding**
```powershell
netsh interface portproxy add v4tov4 listenport=<PORT_YOU_WANNA_LISTEN> listenaddress=<IP_ADDRESS_OF_YOUR_LAP> connectport=<PORT_YOU_WANNA_LISTEN> connectaddress=<IP_ADDRESS_TO_YOUR_WSL>
```
**Delete port forwarding**
```powershell
netsh interface portproxy delete v4tov4 listenaddress=<IP_ADDRESS_YOU_WERE_LISTENING> listenport=<PORT_YOU_WERE_LISTENING>
```