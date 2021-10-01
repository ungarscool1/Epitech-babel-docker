# escape=`

FROM mcr.microsoft.com/windows:1809

SHELL ["cmd", "/S", "/C"]

ADD https://aka.ms/vs/16/release/vs_buildtools.exe C:\Temp\vs_buildtools.exe
ADD https://aka.ms/vs/16/release/channel C:\Temp\VisualStudio.chman
ADD https://github.com/conan-io/conan/releases/latest/download/conan-win-64.exe C:\TEMP\conan.exe

RUN C:\Temp\vs_buildtools.exe `
    --quiet --wait --norestart --nocache `
    --channelUri C:\Temp\VisualStudio.chman `
    --installChannelUri C:\Temp\VisualStudio.chman `
    --add Microsoft.VisualStudio.Workload.VCTools;includeRecommended `
    --add Microsoft.Component.MSBuild `
    --add Microsoft.VisualStudio.Component.VC.CMake.Project `
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

RUN C:\TEMP\conan.exe /SILENT /NOCANCEL /NORESTART /NOICONS

ENTRYPOINT ["C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\BuildTools\\Common7\\Tools\\VsDevCmd.bat", "&&", "powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]