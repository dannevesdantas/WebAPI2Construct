WebAPI2Construct
================

WebAPI2Construct simplifies the integration of ASP.NET Web API with Construct 2 game engine by Scirra

## Get it on NuGet!

    Install-Package WebAPI2Construct

## How to use
### Convert a C# object to the Construct2 Dictionary format

```
PlayerData playerData = new PlayerData(); // An example object with the data to be sent to the game

// Use WebAPI2Construct to put tour data in the Construct 2 readable format
var playerDataJSON = Construct2Convert.ToDictionary(playerData);

return playerDataJSON; // Send the data to the game
```
