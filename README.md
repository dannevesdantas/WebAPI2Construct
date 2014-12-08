WebAPI2Construct
================

WebAPI2Construct simplifies the integration of [ASP.NET Web API](http://www.asp.net/web-api) with [Construct 2 game engine by Scirra](https://www.scirra.com/construct2)

## What can it be used for?
If you are developing a game with Construct 2 game engine and want to save, load, delete or update game's data from a server and/or a database you can use Microsoft ASP.NET WEB API with WebAPI2Construct to format the game's data in a format that Construct 2 can understand when sending it from the ASP.NET server to the game.

## Get it on NuGet!
    
    Install-Package WebAPI2Construct
    
## How to Use
### Converting a C# object to Construct2 Dictionary format

###### First Pass: Visual Studio
1. If you already don't, [download Microsoft Visual Studio for free](http://www.visualstudio.com/pt-br/downloads/download-visual-studio-vs#DownloadFamilies_2)
2. [Create a new project](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api), or open an existing [ASP.NET WEB API](http://www.asp.net/web-api) project.
3. [Install WebAPI2Construct via NuGet Package Manager](https://www.youtube.com/watch?v=02LQNppYVx0)
4. Set up the CORS in your project, see [how to set up CORS in a WEB API project](http://www.asp.net/web-api/overview/security/enabling-cross-origin-requests-in-web-api)
5. Disable XML formatter inside the *Register* method in the *WebAPIConfig.cs*, it can be found at *App_Start* project's folder. It will make JSON the default format:

```
// Use JSON as the default response format
config.Formatters.Remove(config.Formatters.XmlFormatter); // Disable the XML formatter
```

4. Use the ```Construct2Convert.ToDictionary()``` to convert objects or collections like arrays to a Construct2 Dictionary data format, example:

```
PlayerData playerData = new PlayerData(); // An example object with the data to be sent to the game
playerData.PlayerName = "John";
playerData.HiScore = 999;

// Use WebAPI2Construct to put your data in Construct2 readable format
var playerDataJSONDictionary = Construct2Convert.ToDictionary(playerData);

return Ok(playerDataJSONDictionary); // Send the data to the game
```

###### Second Pass: Construct 2
2. When in Construct 2, use an [AJAX object](https://www.scirra.com/manual/107/ajax) *Request URL* action to request the data to ASP.NET WEB API service's address.
3. Catch the data in the game using the AJAX *On completed* event
4. Use a [Dictionary](https://www.scirra.com/manual/140/dictionary) object *Load* action to load the data from the *AJAX.LastData* variable
5. After that you be able to read your data from inside the [Dictionary](https://www.scirra.com/manual/140/dictionary)

### Why using Construct 2 Dictionaries?
Using a Dictionary you will be able to pass more complex data to the game, at the same time.

## LICENSE
[Apache 2.0 License](https://github.com/dannevesdantas/WebAPI2Construct/blob/master/LICENSE)
