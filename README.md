WebAPI2Construct
================

WebAPI2Construct simplifies the integration of ASP.NET Web API with Construct 2 game engine by Scirra

## What can it be used for?
If you are developing a game in the Construct 2 game engine and want to save, load, delete ou update information from a server and/or a database you can use Microsoft ASP.NET WEB API with WebAPI2Construct to format the game's data in a format that Construct 2 can understand when sending it from the ASP.NET server to the game.

## Get it on NuGet!
    
    Install-Package WebAPI2Construct
    
## How to Use
### Converting a C# object to Construct2 Dictionary format

###### First Pass: Visual Studio
1. If you already don't have, [download Microsoft Visual Studio for free](http://www.visualstudio.com/pt-br/downloads/download-visual-studio-vs#DownloadFamilies_2) and [create a new](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api), or use an existing [ASP.NET WEB API](http://www.asp.net/web-api) project and [install WebAPI2Construct via NuGet Package Manager](https://www.youtube.com/watch?v=02LQNppYVx0)
2. Set up the CORS in your project, see [how to set up CORS in a WEB API project](http://www.asp.net/web-api/overview/security/enabling-cross-origin-requests-in-web-api)
3. Use the Construct2Convert.ToDictionary() to convert objects or collections, like Arrays, to a Construct2 Dictionary data format

```
PlayerData playerData = new PlayerData(); // An example object with the data to be sent to the game
playerData.PlayerName = "John";
playerData.HiScore = 999;

// Use WebAPI2Construct to put your data in Construct2 readable format
var playerDataJSONDictionary = Construct2Convert.ToDictionary(playerData);

return playerDataJSONDictionary; // Send the data to the game
```

###### Second Pass: Construct 2
2. When in Construct 2, use an AJAX object "Request URL" action to request the data to ASP.NET WEB API service's address.
3. Catch the data in the game using the AJAX "On completed" event
4. Use a Dictionary object "Load" action to load the data from the AJAX.LastData variable
5. After that you be able to read your data inside the Dictionary

### Why using Construct 2 Dictionaries?
Using an Dictionary you will be able to pass more complex data to the game, at the same time.

## LICENSE
[Apache 2.0 License](https://github.com/dannevesdantas/WebAPI2Construct/blob/master/LICENSE)
