Общий вид команд для установки: 
```bash
curl https://raw.githubusercontent.com/home-assistant/supervised-installer/master/installer.sh > installer.sh
sudo chmod +x ./installer.sh
sudo bash -x ./installer.sh -s -- -p /home/artur -d $PREFIX/smarthome/hassio
```
Частный конфиг для Ubuntu:
```bash
curl https://raw.githubusercontent.com/home-assistant/supervised-installer/master/installer.sh | bash -x ./installer.sh -s -- -p /home/artur/smarthome -d $PREFIX/hassio
```
Частный конфиг Debian 10 (в настоящее время работает):
```bash
curl -sL https://raw.githubusercontent.com/home-assistant/supervised-installer/master/installer.sh | bash -s -  -d /home/artur/smarthome/hassio
```

# This installation method is for advanced users only

## Make sure you understand [the requirements](https://github.com/home-assistant/architecture/blob/master/adr/0014-home-assistant-supervised.md)

# Install Home Assistant Supervised

This installation method provides the full Home Assistant experience on a regular operating system. This means, all components from the Home Assistant method are used, except for the Home Assistant Operating System. This system will run the Home Assistant Supervisor. The Supervisor is not just an application, it is a full appliance that manages the whole system. It will clean up, repair or reset settings to default if they no longer match expected values.

By not using the Home Assistant Operating System, the user is responsible for making sure that all required components are installed and maintained. Required components and their versions will change over time. Home Assistant Supervised is provided as-is as a foundation for community supported do-it-yourself solutions. We only accept bug reports for issues that have been reproduced on a freshly installed, fully updated Debian with no additional packages.

This method is considered advanced and should only be used if one is an expert in managing a Linux operating system, Docker and networking.

## Installation

Run as root (sudo su):

```bash
curl -Lo installer.sh https://raw.githubusercontent.com/home-assistant/supervised-installer/master/installer.sh
bash installer.sh
```

### Command line arguments
| argument           | default                                                                                                                                                                             | description                                            |
|--------------------|----------------------|--------------------------------------------------------|
| -m \| --machine    |                      | On a special platform they need set a machine type use |
| -d \| --data-share | $PREFIX/share/hassio | data folder for hass.io installation                   |
| -p \| --prefix     | /usr                 | Binary prefix for hass.io installation                 |
| -s \| --sysconfdir | /etc                 | Configuration directory for hass.io installation       |

you can set these parameters by appending ` --<parameter> <value>` like:

```bash
curl -Lo installer.sh https://raw.githubusercontent.com/home-assistant/supervised-installer/master/installer.sh
bash installer.sh --machine MY_MACHINE
```
