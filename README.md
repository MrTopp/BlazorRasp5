# BlazorRasp5

Enkel applikation för deploy i Raspberry Pi 5 med Blazor och .NET 10.

Standard .NET 10 Blazor applikation utan ändringar. Används
för deploy i raspberry 5 med nginx som frontend server.

## Miljö
Svarar på port 5103 i produktionsmiljö. Triggas när
ASPNETCORE_ENVIRONMENT är satt till Production.

## Deploy
För att deploya applikationen, kör följande kommando i terminalen:
```
dotnet publish -c Release -r linux-arm64 --self-contained false
```

