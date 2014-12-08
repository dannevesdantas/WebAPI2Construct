WebAPI2Construct
================

WebAPI2Construct simplifies the integration of ASP.NET Web API with Construct 2 game engine by Scirra

## Get it on NuGet!
    
    Install-Package WebAPI2Construct
    
## How to Use
### Converting a C# object to Construct2 Dictionary format

```
PlayerData playerData = new PlayerData(); // An example object with the data to be sent to the game
playerData.PlayerName = "John";
playerData.HiScore = 999;

// Use WebAPI2Construct to put your data in Construct2 readable format
var playerDataJSON = Construct2Convert.ToDictionary(playerData);

return playerDataJSON; // Send the data to the game
```

## LICENSE
[Apache 2.0 License](https://github.com/danilondantas/WebAPI2Construct/blob/master/LICENSE)
