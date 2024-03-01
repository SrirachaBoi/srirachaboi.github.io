# Mainstream Quickstart

You're not a dev. You're just a rider. You just want this project running as quick as possible.

This guide was made to help.

Once you get the program running, here another guide that contains detailed instructions for backing up and flashing your board: https://www.fixmypev.com/diy/onewheel/rewheel/

## Notice

This fork was created without the permission or knowledge of the original developers. The nature of open source software is to be able to tweak it. Thanks to all contributors, and sorry if I butchered your software.

This software was written to be in compliance with the Digital Millennium Copyright Act (DMCA) and respect all intellectual property rights. While this program strives to operate within legal boundaries, users are advised to exercise caution and ensure their actions do not infringe on any copyright laws. Sharing firmware files, encryption keys, or bootloader backups may not be legal in your jurisdiction.

## Thanks

Thanks to all the open source developers, hackers, and contributors, whose skill and passion made this possible. Thanks to FM for taking the original idea of a single-wheeled board and creating such a compelling device.

## Prerequisites

- Chrome
- A computer (Sorry GenZ-ers, you'll need a legitimate computer to run this)
- node.js (see instructions for your operating system)

## Step 1: Install node.js: Mac and Linux

the recommended method is NVM: https://github.com/nvm-sh/nvm#install--update-script
If you're too lazy to read their documentation, simply run these commands in your terminal:

```shell
# you might need to prefix the following command with "sudo" if it complains
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

Next, close your terminal and re-open it.
Run:

```shell
nvm install 18
nvm use 18
nvm alias default 18
```

Now that you have node.js installed, verify it works by running:

```shell
# this will give you the versions of your node and npm
node -v
npm -v
```

### Troubleshooting node.js install

If that doesn't work, you'll need to make sure the following is in your profile file (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc depending on your system):

```shell
# don't run the following command, you're going to need to google how to do this part, or read the NVM documentation
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

## Step 1: Install node.js: Windows

Download and install the LTS version of node.js: https://nodejs.org/en/download

## Step 2: Using node.js To Install http-server

```shell
npm install --global http-server
```

### Step 3: Using node.js to Run http-server

Finally, the last step (and the only step you need to repeat every time you want to run this project).
Open a terminal window into the same directory that you extracted the application into.

You should be in the same directory that this document is located in.

Run:

```shell
http-server --tls --cert certificates/server.pem --key certificates/private.key
```

Your browser will automatically open to the correct URL (and if not, your terminal will tell you the right URL). If something besides Chrome opens, copy the URL and paste it into Chrome.

Your browser will warn you about a security problem - that's because we're using a self-signed certificate to host the HTTPS server. Simply tell it to ignore the problem and proceed to the website.

NOTES: ignoring this security problem is OK only in this instance since you are running a server locally. Never proceed past the security warning if you see this during your normal web browsing. Do not host a public website using these keys.

If your computer does not have bluetooth, then you will need to connect your phone (only Android supported) to your computer's home network. Then visit this program by navigating to your computer's IP address.

### Step 4: Loading Keys

You need an existing legal backup of your board to extract the keys, or you need to have a legal copy of the keys.

You can upload your backup in the Extras > Key Extractor page. You can then click "Extract", then "Save" in order to save the key to the page's memory.

#### Step 4a: Getting a Backup

Go to the Backup page.

Upload a copy of the OTA file for the model of board you are attempting to back up (Pint, XR, or GT).

Connect to your board, and Flash the Extractor.

NOTE: Some boards (GTs) will error out at this stage and require a second Extractor flash. GTs may flash rainbow colors. If this happens, you should power-cycle the board and attempt to flash the Extractor a second time.

Extract your board's bootloader, which will take a while.
When that's done, also extract the board's settings, which will be faster.
Lastly, click SAVE and download your backup.

### Step 5: Patching Firmware

Once keys have been entered, proceed to the Patch page.

There, you upload the firmware and select which patches you would like.
Create and save the firmware to your computer.

### Step 6: Flashing

Remember, this step might brick your board. Use caution.

Power up your board, connect to bluetooth, and then go to the Flash page to upload your patched firmware.

Keep your phone or computer as close to your board as possible. Do not allow either to power off or go to sleep.

If you have a GT, then during flashing, your board will first turn rainbow-colored lights, then turn yellow. While it is yellow, it is flashing. The number of yellow lights indicate the progress of the flash. Wait for the board lights to turn all white again.

NOTE: Some GTs will enter a failed flashing rainbow lights state upon first attempt, and will require two attempts to succeed. Simply power-cycle the board, reload the page, and attempt to flash the same firmware again.

If flashing fails multiple times in a row, try to power off the board and back on.and reload the page, then flash stock firmware.
