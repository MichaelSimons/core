FROM microsoft/dotnet:1.0.0-nanoserver-core

# Add dotnetbot application
WORKDIR /dotnetbot
ADD artifacts .

ENTRYPOINT ["dotnet", "dotnetbot.dll"]
