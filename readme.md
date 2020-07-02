Perf testing with dotnet core

https://channel9.msdn.com/Shows/On-NET/ASPNET-Core-Series-Performance-Testing-Techniques?ocid=3006539&MC=ASPNET&MC=Vstudio&MC=.NET&MC=Testing&MC=CloudDev#time=18m38s

Install dontet counters:


```bat
dotnet tool install --global dotnet-counters
```

docs:
https://docs.microsoft.com/en-us/dotnet/core/diagnostics/dotnet-counters

run the app:
```bat
dotnet run
```

Run dotnet counters - just remember to pass propper process-id

```bat
dotnet counters monitor --process-id 32196 System.Runtime Microsoft.AspNetCore.Hosting 
```

execute load:

```bat
c:\tools\bombardier-windows-386.exe -c 500 -d 30s -l --rate 500  https://localhost:5001/weatherforecast
```