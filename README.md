 


# How to play with offline server

1. Clone from and install https://github.com/thepeacockproject/linux-steam-setup
   - mkdir -p ~/.config/systemd/user
   - cp peacock.service ~/.config/systemd/user/ 
     - if installer moved change location in service
   - systemctl --user enable --now peacock
   - systemctl --user start peacock
   - systemctl --user status peacock

2. To play run hitman 3 launcher (dont press play)
3. After hitman 3 launcher runs, run launch.peacock.sh script to launch peacock exe
4. Done

If there are errors like cant connect, change server from peacock local to 127.0.0.1:3000


## Scripts used:

### Hitman 3 launch options, it is with ZHModSDK, main part STEAM_COMPAT_LAUNCHER_SERVICE=proton
DXVK_FRAME_RATE=60 WINEDLLOVERRIDES="dinput8,ZHMModSDK=n,b" STEAM_COMPAT_LAUNCHER_SERVICE=proton %command%

### Sniper location + app id + exe location 
/home/dovydas/.steam/debian-installation/steamapps/common/SteamLinuxRuntime_sniper/pressure-vessel/bin/steam-runtime-launch-client \
--bus-name=com.steampowered.App1659040 \
-- wine /home/dovydas/Desktop/Hitman-3-Offline-Server/linux-steam-setup/Peacock/PeacockPatcher.exe
