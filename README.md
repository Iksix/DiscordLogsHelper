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
