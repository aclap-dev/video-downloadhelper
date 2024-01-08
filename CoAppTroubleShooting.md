# DownloadHelper CoApp - Troubleshooting

If the coapp is not recognised by the extension, here are a few things you can try:

- Try the latest coapp. You will find the download links [here](https://www.downloadhelper.net/install-coapp-v2).
- If you use Edge, make sure to install the addon from the Microsoft store, not the Google store. See relevant links [here](https://www.downloadhelper.net/install).

## Windows 7

We have dedicated builds for Windows 7. You will find the download links [here](https://www.downloadhelper.net/install-coapp-v2). **Make sure to install the Windows 7 version** (_vdhcoapp-xxx-win7-x86_64-installer.exe_).

## Mac

After install, start the coapp (only on time after intallation), this should re-register the app in the relevant browsers.
If you use an old version of MacOS, [see this](https://github.com/aclap-dev/vdhcoapp/issues/190).

## Ubuntu (and Flatpak / Snap based distributions)

Most of the time, the issue is a missed prompt. Firefox should have showed you a prompt to allow the coapp to communicate with the extension. Some people miss the prompt, or the prompt just never shows up. There's no user interface to change that setting. To solve this, run these commands (even if you don't use Flatpak):

```
sudo apt-get install -y flatpak
flatpak permission-set webextensions net.downloadhelper.coapp snap.firefox yes
```

Also:

- Run `/opt/vdhcoapp/vdhcoapp install` (**not as root! Don't use sudo**) to re-register the app.
- Move to the installation folder of the coapp in your terminal, and run: `./vdhcoapp --info`. It will run some diagnostic operations.
- do not install vdhcoapp within the `/usr/` directory, it won't be detected by your browser. [See here why](https://github.com/aclap-dev/vdhcoapp/issues/160#issuecomment-1780765719).
- **Snap Chromium-based browsers**: they do not support native messaging yet. It is up to Google to fix this issue.

## Linux (generic)

- Run `/opt/vdhcoapp/vdhcoapp install` (**not as root! Don't use sudo**) to re-register the app.
- Move to the installation folder of the coapp in your terminal, and run: `./vdhcoapp --info`. It will run some diagnostic operations.

