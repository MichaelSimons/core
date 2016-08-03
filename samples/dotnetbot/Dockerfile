FROM nanoserver

# Install .NET Core
ENV DOTNET_CORE_SDK_VERSION 1.0.0
ADD https://dotnetcli.blob.core.windows.net/dotnet/preview/Binaries/$DOTNET_CORE_SDK_VERSION/dotnet-win-x64.$DOTNET_CORE_SDK_VERSION.zip dotnet.zip
RUN powershell -NoProfile [System.IO.Compression.ZipFile]::ExtractToDirectory('dotnet.zip', '%ProgramFiles%\dotnet')
RUN setx /M PATH "%PATH%;%ProgramFiles%\dotnet"

# Add forwarders assemblies to workaround https://github.com/dotnet/cli/issues/2967
ADD ["TP5Forwarders/", "/Program files/dotnet/"]

# Add dotnetbot application
WORKDIR /dotnetbot
ADD artifacts .

ENTRYPOINT ["dotnet", "dotnetbot.dll"]
