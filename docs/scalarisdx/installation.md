title: Scalaris DX Installation Guide
description: This guide explains the process for installing Scalaris DX, a decentralized exchange dApp powered by the Blocknet Protocol.

# Scalaris DX Installation
[Scalaris DX](/scalarisdx/introduction) is a decentralized exchange dApp powered by the Blocknet Protocol. Installing the Scalaris DX is a simple process. Below are step-by-step instructions for how to install on each operating system (OS). If you already have Scalaris DX installed and are updating, see the updating guide. For a complete guide on setting up Scalaris DX, see the [Scalaris DX setup guide](/scalarisdx/setup).

---

## Install Scalaris DX


??? example "Windows"
	1. Download the [latest Scalaris DX release](https://github.com/scalaris-project/scalaris-dx/releases/). There are 3 Windows options:
		1. `Scalaris-DX-x.x.x-win.exe` (recommended)
		1. `Scalaris-DX-x.x.x-win-x64.zip`
		1. `Scalaris-DX-x.x.x-win-ia32.zip`

	1. Before continuing, it is recommended to [verify your download](/scalarisdx/installation/#verifying-downloads) 
	1. Continue to the instructions below for the download you selected:

	??? example "Using the `.exe` download (option a)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to begin the installation process.
		1. Read the License Agreement and select *Accept* to acknowledge.

		--8<-- "complete-scalarisdx-installation.md"

	??? example "Using the `.zip` download (options b/c)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Right-click the file, select *Extract All*.
		1. Select *Extract*.
		1. After the files are extracted, a new folder should open with the contents. If a folder did not open, look for the new folder in the directory the downloaded file is located.
		1. Here you will find the `Scalaris DX` executable file.
		1. Double-click the `Scalaris DX` file to begin the installation process.
		1. Read the License Agreement and select *Accept* to acknowledge.

		--8<-- "complete-scalarisdx-installation.md"


??? example "MacOS"
	1. Download the [latest Scalaris DX release](https://github.com/scalaris-project/scalaris-dx/releases/). There are 2 MacOS options:
		1. `Scalaris-DX-x.x.x-mac.dmg` (recommended)
		1. `Scalaris-DX-x.x.x-mac.zip`

	1. Before continuing, it is recommended to [verify your download](/scalarisdx/installation/#verifying-downloads) 
	1. Continue to the instructions below for the download you selected:

	??? example "Using the `.dmg` download (option a)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to begin installation.
		1. Click and drag the *Scalaris DX* application icon over to the *Applications* folder and release.
		1. If you are prompted with a message asking if you would like to replace an existing version with a newer version, select *Replace*.
		1. Open *Finder*, navigate to *Applications*, and find *Scalaris* in the list of applications.
		1. Right-click the file and select *Open*. If using the touch pad this can be done by clicking with 2 fingers.
		1. If you are prompted with a message asking if you are sure you want to open the application, select *Open*.
		1. Your computer will begin verifying the application. This may take a few minutes to complete.
		1. Read the License Agreement and select *Accept* to acknowledge.

		--8<-- "complete-scalarisdx-installation.md"

	??? example "Using the `.zip` download (option b)"
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to unpack the contents.
		1. Click and drag the *Scalaris DX* application over to the *Applications* folder and release. This will add it to *Applications*.
		1. If you are prompted with a message asking if you would like to replace an existing version with a newer version, select *Replace*.
		1. The downloaded file may now be removed.
		1. In *Finder*, navigate to *Applications*, and find *Scalaris-DX* in the list of applications.
		1. Right-click the file and select *Open*. If using the touch pad this can be done by clicking with 2 fingers.
		1. If you are prompted with a message asking if you are sure you want to open the application, select *Open*.
		1. Your computer will begin verifying the application. This may take a few minutes to complete.
		1. Read the License Agreement and select *Accept* to acknowledge.

		--8<-- "complete-scalarisdx-installation.md"


??? example "Linux"
	1. Download the [latest Scalaris DX release](https://github.com/scalaris-project/scalaris-dx/releases/). There are 2 Linux options:
		1. `Scalaris-DX-x.x.x-linux.deb` (recommended)
		1. `Scalaris-DX-x.x.x-linux.tar.gz` (Gzip archive)

	1. Before continuing, it is recommended to [verify your download](/scalarisdx/installation/#verifying-downloads) 
	1. Continue to the instructions below for the download you selected:

	??? example "Using the `.deb` download (option a)"
		1. You may be asked for a confirmation to download, select *Save File* then *OK*.
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Double-click the file to open the installation screen.
		1. Select *Install*. 
		1. You may be asked to enter your account password.
		1. The installation process may take a few minutes.
		1. Read the License Agreement and select *Accept* to acknowledge.

		--8<-- "complete-scalarisdx-installation.md"

	??? example "Using the `.tar.gz` download (option b)"
		1. You may be asked for a confirmation to download, select *Save File* then *OK*.
		1. Find the downloaded file. The default location is in *Downloads*.
		1. Right-click the file, select *Extract Here*.
		1. Double-click the `Scalaris-DX-x.x.x-linux/` folder to view the contents.
		1. Here you will find the `block-dx` executable file.
		1. Double-click the `block-dx` file to install.
		1. Read the License Agreement and select *Accept* to acknowledge.
		
		--8<-- "complete-scalarisdx-installation.md"

## Verifying Downloads

It is important to verify the integrity of downloads before running them. Depending on how you downloaded it, it's possible the file may have been modified in transit to do something evil when run. The server hosting the download may also have been compromised.

1. Get the sha256 hash of the release you download. These are provided
on the Github release page as
[plain text in the release notes](https://github.com/scalaris-project/scalaris-dx/releases/). The
format follows `SHA256-hash <filename>`. Here is an example of the hashes:
```
4a6bd1ad96edf6b052e9929633f978a9a06c85552091a5df1e9bf0bda18ee449  Scalaris-DX-1.0.0-linux-amd64.deb
d90ad1ff0797fc30d749597252718cb7c52843e1020818edb2fbb2a8dbaf95d0  Scalaris-DX-1.0.0-linux-armv7l.AppImage
9fdda89ef175621e052b6ff8dbb6ab0826c6bc85e1f380c0ea967f638577373b  Scalaris-DX-1.0.0-linux-x64.tar.gz
2d23161771b6bcec2a6c6242e872638ac7c6be7864f4bb74df4d7af723716a94  Scalaris-DX-1.0.0-linux-x86_64.AppImage
83e07323a04873a96264f6f46f541956adfa0f86d17986d6278f773660e704db  Scalaris-DX-1.0.0-mac.dmg
6e8211d56204acd155273c19329eea629ff5fc6195e178e026734cc3b3ce354f  Scalaris-DX-1.0.0-mac.zip
45b239611cd4e248d291cd33a9ac7dede927ed4313b29d3eb5728c38420066f2  Scalaris-DX-1.0.0-win-ia32.zip
cc29caeae49b6f99e28b36f64e678267be46a14526fbef4a311acc215aaa3c79  Scalaris-DX-1.0.0-win-x64.zip
8be6d4bde7fa182d68047524671ac61b3366c9b3e8f241bf2493e001fa3502ef  Scalaris-DX-1.0.0-win.exe
```
1. Take a note of the hash for the specific file you downloaded.
1. Get the sha256 hash of the file you downloaded:

	??? example "Windows"
		1. Open the command prompt.
		1. Navigate to the location of the downloaded file.
		1. Enter `certUtil -hashfile filename SHA256` with `filename` replaced by the name fo the file you downloaded. 
		
		**Example**: `certUtil -hashfile Scalaris-DX-1.0.0-win.exe SHA256`

	??? example "MacOS"
		1. Open the terminal.
		1. Navigate to the location of the downloaded file.
		1. Enter `shasum -a 256 filename` with `filename` replaced by the name fo the file you downloaded. 
		
		**Example**: `shasum -a 256 Scalaris-DX-1.0.0-mac.dmg`

	??? example "Linux"
		1. Open the terminal.
		1. Navigate to the location of the downloaded file.
		1. Enter `sha256sum filename` with `filename` replaced by the name fo the file you downloaded. 
		
		**Example**: `sha256sum Scalaris-DX-x.x.x-linux.deb`

1. Compare the release hash to the hash of the download. If the hashes do not match, **DO NOT** run the file and delete the file immediately.






<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





