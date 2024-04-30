## Example
```csharp
Task.Run(async () =>
  {
      await DiscordLogsHelper.SendToDiscord("voteStart", new()
      {
          {"targetName", target.PlayerName},
          {"targetId", target.SteamId.SteamId64.ToString()},
          {"playerName", callerInfo.PlayerName},
          {"playerId", callerInfo.SteamId.SteamId64.ToString()},
          {"action", GetActionString(action)},
          {"reason", reason}
      });
  });
```
## In config
```csharp
public string DiscordWebHook { get; set; } = "";
public string DiscordAuthor { get; set; } = "TEST SERVER";

public Dictionary<string, EmbedModel> Embeds { get; set; } = new()
{
    {"voteStart", new EmbedModel("Title", "desc", new ColorModel(0, 255, 0), new []{ new FieldModel("fieldName", "content", false) })}
};
```
## On Config parsed
```csharp
public void OnConfigParsed(PluginConfig config)
{
    Config = config;
    DiscordLogsHelper.WebHook = Config.DiscordWebHook;
    DiscordLogsHelper.Author = Config.DiscordAuthor;
    DiscordLogsHelper.Embeds = Config.Embeds;
}
```

