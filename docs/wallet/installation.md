title: Scalaris Wallet Installation Guide
description: This guide explains how to install your Scalaris wallet on each operating system to securely manage your SCA through a wallet you own.


# Wallet Installation
Installing the [Scalaris wallet](https://github.com/scalaris-project/scalaris/releases) is a simple process. Choise wallet for your system and install.

* For a complete guide on setting up the wallet, see the [setup guide](/wallet/setup).

??? tip "Tip: There are two wallet variations."
	There are two wallet variations, a redesigned interface (default) and a classic interface. To use the classic wallet, you'll need to open your `scalaris.conf` file and add `classic=1` on a new line (you may not have a `scalaris.conf` file and will need to create one). You can find the `scalaris.conf` file in your Scalaris data directory:

	--8<-- "data-directories.md"

---

## Install GUI Wallet

??? example "Windows"

	1. Download the [latest Scalaris wallet](https://github.com/scalaris-project/scalaris/releases/). There are 4 options:

		1. `scalaris-x.xx.x-win64-setup-unsigned.exe` (recommended for 64-bit)
	1. `scalaris-x.xx.x-win32-setup-unsigned.exe` (recommended for 32-bit)
	1. `scalaris-x.xx.x-win64.zip`
	1. `scalaris-x.xx.x-win32.zip`

	    --8<-- "anti-virus-flagged.md"

	1. Before continuing, it is recommended to [verify your download](/wallet/installation/#verifying-downloads)
	1. Continue to the instructions below for the download you selected:

	??? example "Using the `.exe` download (options a/b)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to begin the installation process.

			???+ info "Note: You may receive antivirus warning messages."
				You may recieve warnings from antivirus software. These false positives are normal and can be dismissed.

				If you have Windows SmartScreen enabled, you may see the following message:

				![SmartScreen](/img/wallet/win-protected.jpg)

				Select *More info*, then *Run anyway* to dismiss this message:

		1. The installation guide will appear, select *Next*.

		1. Select *Next* to accept the default installation directory.


		1. Select *Install* to accept the default data directory folder name and begin installation.


		1. Select *Next* when the installation is complete.


		1. Select *Finish* to complete the installation process. If you would not like the wallet to open right away, uncheck the *Run Scalaris* option.


		--8<-- "complete-wallet-installation.md"

	??? example "Using the `.zip` download (options c/d)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Right-click the file, select *Extract All*.
		1. Select *Extract*.
		1. After the files are extracted, a new folder should open with the contents. If a folder did not open, look for the new folder in the directory the downloaded file is located.
		1. In this new folder there will be another folder. Double-click on this sub-folder to view the contents.
		1. In this folder there will be a `bin/` folder. Double-click on this sub-folder to view the contents.
		1. Here you will find the `scalaris-qt` executable file.
		1. Move this file you where you keep your applications, such as your *Desktop*. Additionally, you can right-click and *Pin to Start* or *Pin to Taskbar* for easy access.
		1. After moving this file, the files you downloaded can be deleted since the `scalaris-qt` executable file is all that is needed.
		1. Double-click the `scalaris-qt` file to begin the run wallet.

			???+ info "Note: You may receive antivirus warning messages."
				You may recieve warnings from antivirus software. These false positives are normal and can be dismissed.

				If you have Windows SmartScreen enabled, you may see the following message:

				![SmartScreen](/img/wallet/win-protected.jpg)

				Select *More info*, then *Run anyway* to dismiss this message:


		--8<-- "complete-wallet-installation.md"



??? example "MacOS"
	1. Download the [latest Scalaris wallet](https://github.com/scalaris-project/scalaris/releases/). There are 3 options:

		1. `scalaris-x.xx.x-osx-unsigned.dmg` (recommended)
	1. `scalaris-x.xx.x-osx-unsigned.tar.gz`
	1. `scalaris-x.xx.x-osx64.tar.gz`

	    --8<-- "anti-virus-flagged.md"
		<!-- !!! bug "Bug: MacOS"
			The `.dmg` download is unavailable for the latest release. Use the `osx-unsigned.tar.gz` download instead (see guide below). -->

	1. Before continuing, it is recommended to [verify your download](/wallet/installation/#verifying-downloads)
	1. Continue to the instructions below for the download you selected:

	??? example "Using the `osx-unsigned.dmg` download (option a)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to begin installation.
		1. Click and drag the *Scalaris-Qt* application icon over to the *Applications* folder and release.
		1. Open *Finder*, navigate to *Applications*, and find *Scalaris-Qt* in the list of applications.
		1. Right-click the file and select *Open*. If using the touch pad this can be done by clicking with 2 fingers.
		1. If you are prompted with a message asking if you are sure you want to open the application, select *Open*.
		1. Your computer will begin verifying the application. This may take a few minutes to complete.
		1. An installation prompt will appear, select *OK*.
		1. Run scalaris wallet.
		--8<-- "complete-wallet-installation.md"

	??? example "Using the `osx-unsigned.tar.gz` download (option b)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to unpack the contents.
		1. In the newly unpacked folder, navigate to the *dist* folder.
		1. Click and drag the *Scalaris-Qt* application over to the *Applications* folder and release. This will add the wallet to *Applications*.
		1. If you are prompted with a message asking if you would like to replace an existing version with a newer version, select *Replace*.
		1. The downloaded files may now be removed.
		1. Open *Finder*, navigate to *Applications*, and find *Scalaris-Qt* in the list of applications.
		1. Right-click the file and select *Open*. If using the touch pad this can be done by clicking with 2 fingers.
		1. If you are prompted with a message asking if you are sure you want to open the application, select *Open*.
		1. Your computer will begin verifying the application. This may take a few minutes to complete.
		1. An installation prompt will appear, select *OK*.
        1. Run scalaris wallet.

		--8<-- "complete-wallet-installation.md"

	??? example "Using the `osx64.tar.gz` download (option c)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to unpack the contents.
		1. In the new folder created, navigate to the `bin/` folder.
		1. Double-click the `scalaris-qt` file.
		1. If you are prompted with a message asking if you are sure you want to open the application, select *Open*.
		1. Your computer will begin verifying the application. This may take a few minutes to complete.
		1. Since this is a command line executable file, a command-line window will appear to start the wallet, which begins the installation process.
		1. An installation prompt will appear, select *OK*.
        1. Run scalaris wallet.
		
		--8<-- "complete-wallet-installation.md"



??? example "Linux"
	1. Download the [latest Scalaris wallet](https://github.com/scalaris-project/scalaris/releases/). There are 3 options:

		1. `scalaris-x.xx.x-x86_64-linux-gnu.tar.gz` (recommended for 64-bit)
	1. `scalaris-x.xx.x-i686-pc-linux-gnu.tar.gz` (recommended for 32-bit)
	1. `scalaris-x.xx.x-arm-linux-gnueabihf.tar.gz` (recommended for Raspberry Pi)

	    --8<-- "anti-virus-flagged.md"

	1. You may be asked for a confirmation to download, select *Save File* then *OK*.
	1. Find the downloaded file. The default location is in *Downloads*.
	1. Before continuing, it is recommended to [verify your download](/wallet/installation/#verifying-downloads) 
	1. Right-click the file, select *Extract Here*.
	1. Double-click the `scalaris-x.xx.x-x86_64-linux-gnu/` folder to view the contents.
	1. Double-click the `scalaris-x.xx.x/` folder to view the contents.
	1. Double-click the `bin/` folder to view the contents.
	1. Here you will find the `scalaris-qt` executable file.
	1. Move this file you where you keep your applications, such as your *Desktop*.
	1. After moving this file, the files you downloaded can be deleted since the `scalaris-qt` executable file is all that is needed.
	1. Double-click the `scalaris-qt` file to begin the installation
       process. (If it fails to open on double-click, you may need to give
       *executable* permission to the file: Either `sudo chmod +x
       scalaris-qt` in Debian terminal, or Right-click property, give
       executable permission.)
	1. An installation prompt will appear, select *OK*.
    1. Run scalaris wallet.

	--8<-- "complete-wallet-installation.md"


<!--
---

## Install CLI Wallet

??? example "Windows"


??? example "MacOS"
	

??? example "Linux"
-->	

---

## Verifying Downloads

It is important to verify the integrity of downloads before running them. Depending on how you downloaded it, it's possible the file may have been modified in transit to do something evil when run. The server hosting the download may also have been compromised.

1. Get the sha256 hash of the release you download. These are provided on the Github release page either in a file called `sha256sums.txt` or as a plain text in the release notes. The format follows `SHA256(filename)= hash`. Here is an example of the hashes:
```
53B3B4CA8688EE81284D3DE8C585038BBA776EB1978F5B01C618BE4ED4C43847  scalaris-1.0.0-aarch64-linux-gnu-debug.tar.gz
0D74585ADBCA407B671A2D4F5314A8E3743F45C8BEA89E92E221673C38178EEB  scalaris-1.0.0-aarch64-linux-gnu.tar.gz
CCB060CDFB1C746774DDE597797711FE533A1ECBDDBBC27DDAAF4336D39BD7A2  scalaris-1.0.0-arm-linux-gnueabihf-debug.tar.gz
7DC865B10C7B6AFE1F6E8AF5ADFEAFE7C5303EB13F26775AD8F70EF6AE2FC141  scalaris-1.0.0-arm-linux-gnueabihf.tar.gz
1BD5008C6F5928D3E66A30EACC22E92A013E16AD92BA4DEB59EFE910B9686C75  scalaris-1.0.0-osx-unsigned.dmg
6CE1E12F96B47284BA820529203CDAD28F513E851E82EEEB9A9F8BEB8170E2DB  scalaris-1.0.0-osx-unsigned.tar.gz
4DDBF8AFD65CCD737915241E756C67A2F37D6DFA02691A6D6E658C851B66CEA0  scalaris-1.0.0-osx64.tar.gz
29DBB3DC45B260C13BC3BA6B9F19C734959C67859E8B62CD97660CDB11B253B6  scalaris-1.0.0-riscv64-linux-gnu-debug.tar.gz
D929A2F0C90215FF973F5101CA42E75FE1F63E70440D994E2779161C37097651  scalaris-1.0.0-riscv64-linux-gnu.tar.gz
F6E4F4D1ABE5ED23EF3373FFA140C3518E95AB1BCB86ABDDE91D836C84EF9587  scalaris-1.0.0-win-unsigned.tar.gz
2C1EDC6735063A015D9CB7DBC2A21BD1ECFD6E4ED1FE2C7F73CEC3E4A78752B7  scalaris-1.0.0-win64-debug.zip
319305F318F0F9B3BE5A4D3F52EB8E0C47CD952418D948627C1B4F259783B075  scalaris-1.0.0-win64-setup-unsigned.exe
58364BDC30FA791E12E40F5244BCC9DADCA3EC1019F23CC3F54010DD0A8049DD  scalaris-1.0.0-win64.zip
301167FC91699DB555FE84AAE06BE9C4429213907DC4CDB64C88BCDA9B91D57F  scalaris-1.0.0-x86_64-linux-gnu-debug.tar.gz
8A4A2AC9EFB752967ADD9AE9A7F9C17AE879D64BAD5EEF70324937FE021E3FB7  scalaris-1.0.0-x86_64-linux-gnu.tar.gz
```
1. Take a note of the hash for the specific file you downloaded.
1. Get the sha256 hash of the file you downloaded:

	??? example "Windows"
		1. Open the command prompt.
		1. Navigate to the location of the downloaded file.
		1. Enter `certUtil -hashfile filename SHA256` with `filename` replaced by the name fo the file you downloaded. 
		
		**Example**: `certUtil -hashfile scalaris-1.0.0-win64.zip SHA256`

	??? example "MacOS"
		1. Open the terminal.
		1. Navigate to the location of the downloaded file.
		1. Enter `shasum -a 256 filename` with `filename` replaced by the name fo the file you downloaded. 
		
		**Example**: `shasum -a 256 scalaris-1.0.0-osx-unsigned.tar.gz`

	??? example "Linux"
		1. Open the terminal.
		1. Navigate to the location of the downloaded file.
		1. Enter `sha256sum filename` with `filename` replaced by the name fo the file you downloaded. 
		
		**Example**: `sha256sum scalaris-1.0.0-x86_64-linux-gnu.tar.gz`

1. Compare the release hash to the hash of the download. If the hashes do not match, **DO NOT** run the file and delete the file immediately.









<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"
