# QGroundControl v4.2.0 installation on Ubuntu 20.04
_Exported on 3/20/2026 at 11:42:31 GMT+6 from Cursor (2.6.18)_

---

**User**

how to install qgroundcontrol v4.2.0 on ubuntu 20.04

---

**Cursor**

I’ll look up the official QGroundControl 4.2.0 release assets/install instructions for Ubuntu 20.04, then summarize the simplest (binary/AppImage) path and, if needed, the fallback (build from source) approach.

Next I’ll pull the official QGroundControl v4.2.0 release page to confirm the exact Linux artifact(s) available (e.g., AppImage filename) and then give you the exact Ubuntu 20.04 install commands and required dependencies.

## Install QGroundControl `v4.2.0` (Ubuntu 20.04) via AppImage

### 1) Install prerequisites (one-time)
Run:

```bash
sudo usermod -a -G dialout $USER
sudo apt-get remove modemmanager -y
sudo apt install gstreamer1.0-plugins-bad gstreamer1.0-libav gstreamer1.0-gl -y
sudo apt install libqt5gui5 -y
sudo apt install libfuse2 -y
```

Then **log out and log back in** (so `dialout` group changes apply).

(These commands are the Ubuntu/AppImage prerequisites listed by QGroundControl.)  
Source: [QGC Guide – Download and Install (Ubuntu Linux)](https://docs.qgroundcontrol.com/Stable_V4.4/en/qgc-user-guide/getting_started/download_and_install.html)

### 2) Download the exact `v4.2.0` AppImage
Go to the official release assets for `v4.2.0` and download `QGroundControl.AppImage`:
- [mavlink/qgroundcontrol v4.2.0 release page](https://github.com/mavlink/qgroundcontrol/releases/tag/v4.2.0)

### 3) Make it executable and run it
From the folder where you downloaded it:

```bash
chmod +x ./QGroundControl.AppImage
./QGroundControl.AppImage
```

### If it won’t start
Usually you’ll see a missing-library error (common with AppImages). Re-check that `libfuse2` is installed, and if it still fails, paste the exact error text and I’ll tell you which Ubuntu package(s) to add.

