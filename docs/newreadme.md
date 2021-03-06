<a href="https://minisbett.github.io/ultimate-osu-server-switcher/discord.html"><img src="https://discordapp.com/api/guilds/715149105525030932/widget.png"></a>

<a href="https://minisbett.github.io/ultimate-osu-server-switcher"><img width=128 height=128 align="right" src="https://minisbett.github.io/ultimate-osu-server-switcher/images/icon.png"></a>

# Ultimate Osu Server Switcher V2

The Ultimate Osu Server Switcher is a server switcher that allows you to switch between osu!bancho and a variety of private servers.

These features are currently implemented:

- Switching the server with one click
- Switch n' Start by holding Ctrl when clicking on «Connect» or just starting when clicking on «Already Connected»
- \*Automatically closing and re-starting osu when switching the server
- \*Expanded Discord RPC to show what server you are playing on
- \*Minimizing to the system tray e.g. to avoid loading times on every start  (Can be avoided by holding Ctrl when clicking on the X)
- \*An Account Manager to automatically switch your account when switching server
- \*Autostart with Windows (minimized to the system tray) so you don't have to start the switcher everytime you play osu e.g. when using custom Discord RPC.

**\* Feature is toggleable in the settings**

# How it works

The Program fetches all its informations from the datav2/mirrors.json file, which means its fully expandable even without a software update.

Switching to a different server or even bancho itself is fairly simple. You just choose the server you want to connect to and
click the «Connect» button.

# How to add your server

> **The owner of every server must be on our Discord server because it is necessary for our management.**

If you want to add your server to the server switcher, please follow these two steps.

**Step 1: Create the mirror data**

You need to host a json file with data that we need on your server.
This is the template:
```
{
  "name": "",
  "ip": "",
  "icon_url": "",
  "certificate_url": "",
  "discord_url": "" # Optional
}
```

Please use a common used icon format (like png, jpg, ...) for the icon.\
Other file formats are not supported. The minimum size is 256x256.

The certificate must be encoded in Base64. The correct file extension is .cer.\
If you need to convert your certificate, e.g. when you have the file extension .crt, follow [this tutorial](https://support.comodo.com/index.php?/Knowledgebase/Article/View/361/17/how-do-i-convert-crt-file-into-the-microsoft-cer-format).

The Discord invite url must be an official Discord domain (https://discord.gg/XXX)

**Step 2: Create an issue**

Create an issue here on GitHub and select the issue tag **server request**.\
[Click here](https://github.com/MinisBett/ultimate-osu-server-switcher/issues/new?labels=server%20request) to open a ready-to-go issue.

In that, simply link the URL to the mirror file you created together with your Discord name and a link to your server's homepage.

# Hosts & Certificate Handling

The server you are currently playing on is estimated by the ip that is deposited in the hosts file.
Switching a server includes deinstalling all certificates, modfying the hosts file, followed by installing the corresponding certificate
(if you chose to play on a third-party server).

The certificates will be installed on the local machine, rather than just the local user to avoid a warning prompt the user has to agree with.\
This improves the switching agility to garantue the best user experience. Also why not, the hosts changes apply to
the whole computer too.
