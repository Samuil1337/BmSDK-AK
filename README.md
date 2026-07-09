# BmSDK for Arkham Knight
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE.md)

<img height="656" alt="Screenshot_2026-03-20_142630" src="https://github.com/user-attachments/assets/81eef06f-c08c-4ffb-83d9-522a5e1a4873" />

## 📖 About
BmSDK is a scripting platform for Batman: Arkham Knight, allowing you to extend the game with C# code for custom gameplay and logic.

It provides a full game-mapped API _(RPlayerController, WorldInfo, RGameRI, etc.)_ along with utilities for interacting with the game world. It also provides **lifecycle and input events** (script start, enter menu/game, tick, button press, etc.). Check out the [wiki](../../wiki) for more info!

Also see [BmSDK for Arkham City](https://github.com/etkramer/BmSDK)

## 🚀 Getting started
If you want to play script mods, getting started is simple:
1. Download and install the [.NET 10 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-10.0.3-windows-x64-installer) if you haven't already. Make sure you get the 64-bit version (x64).
2. Download the latest release from [releases](../../releases/latest) and open the .zip file.
3. Inside you'll see two folders: `Binaries` and `BmGame`. Copy both to your game folder (likely `C:\Program Files (x86)\Steam\steamapps\common\Batman Arkham Knight`). There should already be 2 folders in there with the same names.
4. Done, BmSDK is installed! Now to install script mods, simply drop any .cs files into your `BmGame\Scripts` folder.

Keep in mind that script mods can potentially harm your computer. Make sure you only download and install scripts from trusted sources.

### ⚠️ Notice for Epic or GOG users:
Only Steam copies of Arkham Knight are supported currently. EGS/GOG support is being considered, but BmSDK unfortunately does not work on these platforms for the time being.

## 🧩 Setting Up for Mod Development
Follow these steps to set up your environment for building, running, and debugging script mods:
1. Go to [visualstudio.microsoft.com/downloads](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&channel=Stable) and run the Visual Studio Installer.
2. In the Visual Studio Installer, select "**.NET desktop development**" from the _Workloads_ tab.
3. Follow all the steps in the [user setup](#-getting-started-for-users), except you can skip installing .NET because it's already included with Visual Studio.
4. Start Visual Studio and open the solution in `%GameDir%\BmGame\ScriptsDev`.
5. Write your code in any C# source file in `%GameDir%\BmGame\Scripts`.
6. Run your code by pressing **F5** in Visual Studio.
7. Follow the [wiki](../../wiki/Creating-your-first-mod) to write your first script.

## 🛠️ Contributing
To get started contributing to BmSDK, see the wiki for instructions: [Building BmSDK](../../wiki/Building-BmSDK)

## 📋 License
BmSDK is licenced under the [MIT licence](LICENSE.md).
