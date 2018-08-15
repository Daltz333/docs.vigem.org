# Automatically select latest Windows 10 SDK

In the project file (`*.vcxproj`) remove or comment out the `WindowsTargetPlatformVersion` property:

```xml
<PropertyGroup Label="Globals">
  ...
  <!-- <WindowsTargetPlatformVersion>10.0.16299.0</WindowsTargetPlatformVersion> -->
</PropertyGroup>
```

Add this new property group which gets evaluated by VS/MSBuild to the latest installed SDK version:

```xml
<PropertyGroup Condition="'$(WindowsTargetPlatformVersion)'==''">
  <!-- Latest Target Version property -->
  <LatestTargetPlatformVersion>$([Microsoft.Build.Utilities.ToolLocationHelper]::GetLatestSDKTargetPlatformVersion('Windows', '10.0'))</LatestTargetPlatformVersion>
  <WindowsTargetPlatformVersion Condition="'$(WindowsTargetPlatformVersion)' == ''">$(LatestTargetPlatformVersion)</WindowsTargetPlatformVersion>
  <TargetPlatformVersion>$(WindowsTargetPlatformVersion)</TargetPlatformVersion>
</PropertyGroup>
```
