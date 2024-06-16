# Project Plus Flatpak
## Installing
- Download ProjectPlus2.5.2.flatpak from releases
- Install ProjectPlus2.5.2.flatpak (sudo needed for installing single use Flatpak bundle)
```console
sudo flatpak install ProjectPlus2.5.2.flatpak
```
## Launching
- Launch the ProjectPlus Flatpak (Either search for the app in your menu and click it) or
```console
flatpak run com.projectplusgame.ProjectPlus
```
## Setup
- Set the "Config>Paths>Default ISO:" to your Brawl.iso
- Optionally change graphics options to use fullscreen and set internal resolution higher
- Play "Project+ Offline Launcher.dol" for offline play or use Tools>Start NetPlay... to either connect or host an online game with the"Project+ Netplay Launcher.dol"
## Uninstalling
- Remove ProjectPlus Flatpak
```console
flatpak remove com.projectplusgame.ProjectPlus
```
## Downloading/Cloning this repo
- Click the green button to download zip and extract once downloaded or clone repo with
```console
git clone --recurse-submodules https://github.com/ChrisHobday/com.projectplusgame.ProjectPlus
```
## Building
- Install Flatpak builder
```console
flatpak install flathub org.flatpak.Builder
```
- Install the platform this Flatpak will be using
```console
flatpak install flathub org.freedesktop.Platform//23.08 org.freedesktop.Sdk//23.08
```
- Build the Flatpak with flatpak-builder (Run this from within the com.projectplusgame.ProjectPlus directory)
```console
flatpak run org.flatpak.Builder --force-clean --repo=repo build-dir com.projectplusgame.ProjectPlus.yml
```
## User installation while building
- Replace last Building step with
```console
flatpak run org.flatpak.Builder --force-clean --repo=repo --user --install build-dir com.projectplusgame.ProjectPlus.yml
```
## Building single use Flatpak bundle like in the releases (After having followed the Building steps above)
- Build the Flatpak bundle (Run this from within the com.projectplusgame.ProjectPlus directory after having followed the Building steps above)
```console
flatpak build-bundle repo FasterPPlus.flatpak com.projectplusgame.ProjectPlus
```
## Troubleshooting
- Check if Flatpak is installed
```console
flatpak list | grep ProjectPlus
```
- Enter Flatpak in commandline mode
```console
flatpak run --command=sh com.projectplusgame.ProjectPlus
```