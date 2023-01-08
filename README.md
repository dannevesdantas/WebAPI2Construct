# WebAPI2Construct

WebAPI2Construct simplifies the integration of [ASP.NET Web API](http://www.asp.net/web-api) with [Construct game engine by Scirra](https://www.construct.net/)

## What can it be used for?
If you are developing a game with Construct game engine and want to save, load, delete or update game's data from a server and/or a database you can use Microsoft ASP.NET WEB API with WebAPI2Construct to format the game's data in a format that Construct can understand when sending it from the ASP.NET server to the game.

## How to Use

Use `Construct2Convert.ToDictionary()` method to convert any C# object to a Construct Dictionary formatted object.

```csharp
[Route("player/data")]
[HttpGet]
public async Task<ActionResult<object>> GetPlayerData()
{
    // An example object with the data to be sent to the game
    PlayerData playerData = new PlayerData();
    playerData.PlayerName = "John";
    playerData.HiScore = 999;

    // Use WebAPI2Construct to transform your data in a Construct readable format
    var playerDataJSONDictionary = Construct2Convert.ToDictionary(playerData);

    return Ok(playerDataJSONDictionary); // Send the data to the game
}
```

## Tutorial
Visit Using AJAX object with ASP.NET Web API tutorial at [https://www.construct.net/en/tutorials/using-ajax-object-asp-net-web-832](https://www.construct.net/en/tutorials/using-ajax-object-asp-net-web-832)

## Get it on NuGet
    
    Install-Package WebAPI2Construct

## LICENSE
[Apache 2.0 License](https://github.com/dannevesdantas/WebAPI2Construct/blob/master/LICENSE)
