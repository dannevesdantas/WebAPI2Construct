WebAPI2Construct
================

WebAPI2Construct simplifies the integration of ASP.NET Web API with Construct 2 game engine by Scirra

## Get it on NuGet!
    
    Install-Package WebAPI2Construct
    
## How to Use
### Converting a C# object to Construct2 Dictionary format

1. In an ASP.NET WEB API project, use the Construct2Convert.ToDictionary() to convert objects or collections to a Construct2 Dictionary data format.

```
PlayerData playerData = new PlayerData(); // An example object with the data to be sent to the game
playerData.PlayerName = "John";
playerData.HiScore = 999;

// Use WebAPI2Construct to put your data in Construct2 readable format
var playerDataJSONDictionary = Construct2Convert.ToDictionary(playerData);

return playerDataJSONDictionary; // Send the data to the game
```

2. When in Construct 2, use an AJAX object "Request URL" action to request the data to ASP.NET WEB API
3. Catch the data in the game using the AJAX "On completed" event
4. After that, use an Dictionary object "Load" action to load the data from the AJAX.LastData variable
5. After that you be able to take your data inside the Dictionary

### Why using Construct 2 Dictionaries?
Using an Dictionary you will be able to pass more complex data to the game at the same time.

## LICENSE
[Apache 2.0 License](https://github.com/danilondantas/WebAPI2Construct/blob/master/LICENSE)
