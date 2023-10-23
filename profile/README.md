# HardHat Toolbox
HardHat tolbox is a collection of plugins for HardHat C2, which can be found here https://github.com/DragoQCC/HardHatC2.

The main documentation site contains detailed directions on using and creating plugins https://docs.hardhat-c2.net/.

## Tool Types 
**Assets**: A plugin created to support an implant for HardHat C2 should include the main implant code in whatever language is desired and c# plugins to add relevant information to the team server and client. 

**Modules**: A standalone plugin for the team server or client does not need to be directly related to an implant. It can be in c# or can mainly be the desired language with a small c# connector. 

**Currently, only Assets are available under the current Alpha 0.3 release but support for Modules is planned for the 0.4 release**

# HardHat Tools 

| Name | Tool Type | Language | Client Ready? | Server Ready? | Supported OS | Active Development (Last 90 Days) | 
| --- | ---------- | -------- |  ---------- |  ---------- |  ---------- |  ---------- |
| Rivet | Asset  |  Rust | :white_check_mark:  | :white_check_mark:  |  Windows | :white_check_mark:   |

# Want To Create Your Own Assets? 
Check out the [Asset Development](https://github.com/HardHatToolbox/Asset-Development) Repo or [Docs](https://docs.hardhat-c2.net/toolbox/assets-implants/asset-creation-guide) for templates and guides on getting started. 

# How To Use An Asset? 
1. To use an Asset, follow its directions on its README for any specifics like packages to install, such as Cargo for Rivet, but in general. 
2. `git clone Asset repo link`
3. `git clone https://github.com/DragoQCC/HardHatC2`
4. Navigate to the HardHat repo and run `Dotnet build -c Release`
5. Navigate to the cloned repo for the plugin and edit the `AssetName_ClientPlugin/AssetName.csproj & AssetName_ServerPlugin/AssetName.csproj`  modify the paths for the Client, Team Server, and ApiModels DLLs to be the local copy you just built
6. Navigate to the cloned repo for the plugin and run `dotnet build -c Release`
7. Copy the created DLLs to the clients and team server, typically found in `ClonedRepo\Asset Name\Asset Name_ClientPlugin\bin\Release\net7.0\Asset Name_ClientPlugin.dll` & `ClonedRepo\Asset Name\Asset Name_ServerPlugin\bin\Release\net7.0\Asset Name_ServerPlugin.dll` These should go in the respective `plugins` folders in the HardHatC2Client and TeamServer folders of HardHat  
8. If HardHat is running, navigate to the Setting page on the client and refresh the client and server plugins. You should now be able to build the Asset in the implant build menu and get them to check in and send tasking. 
  If HardHat is not running, just start HardHat, and the plugins are loaded during startup 
