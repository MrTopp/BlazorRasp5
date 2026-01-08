# BlazorRasp5

Tom applikation skapat från Blazor server template. Ingen modifiering
av programkod eller vyer har gjorts. Den finns för att deploya en enkel
applikation på min Raspberry Pi 5 med .NET 10 och nginx som frontend server.

Modifiering av koden är anpassningar till och uppsäkring av driftsmiljön.

Applikationen kan nås från internet via urlen:
http://hemmahostb.asuscomm.com/BlazorRasp5

Anpassningar av applikationen har gjorts i samarbete med Google Gemini
och GitHub Copilot.

## Miljö
Svarar på port 5103 i produktionsmiljö. Triggas när
ASPNETCORE_ENVIRONMENT är satt till Production.

## Deploy
För att skapa deploy av applikationen, kör följande kommando i terminalen:
```
dotnet publish -c Release -r linux-arm64 --self-contained false
```

Deploy till Raspberry Pi 5 sker genom att kopiera innehållet i mappen
bin\Release\net10.0\linux-arm64\publish till målmappen på Raspberry Pi 5.
