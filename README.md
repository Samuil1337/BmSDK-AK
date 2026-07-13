# BmSDK for Arkham Knight

<p align="center">
  <img width="400" height="200" alt="BmSDK-Logo-White" src="https://github.com/user-attachments/assets/f745c502-d89a-4301-9ef8-6bb4e430d0e9#gh-dark-mode-only" />
  <img width="400" height="200" alt="BmSDK-Logo-Black" src="https://github.com/user-attachments/assets/a49ee32a-fa15-4a1b-b4a4-7a7dde5a0695#gh-light-mode-only" />
</p>

## 📖 About
BmSDK is a scripting platform for Batman: Arkham Knight and [Batman: Arkham City](https://github.com/Team-BmSDK/BmSDK), allowing you to extend the game with C# code for custom gameplay and logic.

It gives you access to a full SDK for working with the game and its world, based on the engine's own UnrealScript API - for example, a short script to spawn in Joker near the player:
```cs
using BmSDK;
using BmSDK.BmGame;
using BmSDK.BmScript;

[Script]
public class DemoScript : Script
{
    public override void OnKeyDown(Keys key)
    {
        if (key == Keys.J)
        {
            var playerPawn = Game.GetPlayerPawn();
            var population = Game.GetPopulationManager();
    
            // Spawn Joker in front of the player
            var define = Game.FindObject<RCharacterDefine>("MainCharacterDefines.Villain.JokerHealthy");
            var joker = population.SpawnPawn(
                RPawnVillainThug.StaticClass(),
                define,
                RCharacter_Thug.StaticClass(),
                playerPawn.Location
            );

            // Move Joker in front of the player
            var dir = playerPawn.Rotation.ToDirection() with { Z = 0 };
            joker.Move(dir * 100);
        }
    }
}
```

Check out the [wiki](../../wiki) for more info!

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
