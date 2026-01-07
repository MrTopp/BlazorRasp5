# GitHub Copilot Instructions

## Tech Stack
- **Framework**: .NET 10
- **UI**: Blazor (Interactive Server)
- **Logging**: Serilog
- **Language**: C# 14

## Target environment
- Server: Raspberry Pi 5 (rasp5)
- OS: Ubuntu 25.10
- Framework: .NET 10
- Proxy: Nginx
- Domain: hemmahostb.asuscomm.com
- Local IP: 192.168.1.10
- Security tool: fail2ban
- Local network connection: Wi-Fi
- Hosting: Kestrel behind Nginx reverse proxy
- url: http://hemmahostb.asuscomm.com/BlazorRasp5

## Coding Conventions

### Blazor Components
- Prioritize Blazor components (`.razor`) over MVC Views or Razor Pages.
- Use `[Inject]` for dependency injection in components.
- Implementation logic should generally reside in the `@code` block or a code-behind partial class, not inline in markup.
- Prefer `ElementReference` and `IJSRuntime` only when pure C# solutions are not possible.

### Asynchronous Programming
- Use `async`/`await` for I/O-bound operations.
- Append `Async` suffix to asynchronous method names.
- Pass `CancellationToken` to async methods where appropriate.

### Logging (Serilog)
- Use structured logging (Message Templates) instead of string interpolation.
  - Good: `logger.LogInformation("Processing item {ItemId}", id);`
  - Bad: `logger.LogInformation($"Processing item {id}");`
- Do not use `Console.WriteLine`. Always use `ILogger<T>`.

### Best Practices
- Define scoped services for state that should persist per-circuit (Blazor Server).
- Validate configuration inputs (e.g., `appsettings.json`) early.
- Keep `Program.cs` clean; move complex setup to extension methods if it grows too large.
