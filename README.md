# Radar — POE2Fixer Plugin SDK Example

Minimal radar overlay plugin demonstrating the v6 Plugin SDK. Draws
monsters / NPCs / chests / area transitions and the walkable map onto
the in-game large map.

## What It Does

Hooks into POE2Fixer's plugin system. When enabled, it draws colored
dots on the in-game large map for nearby entities, plus a translucent
walkable-tile overlay. Per-rarity monster colors, NPCs, chests
(closed vs opened), and area transitions are configurable from the
Plugins settings tab inside POE2Fixer.

## Building

Open `Radar.sln` in Visual Studio 2022. Build Release|x64. Output:

    bin/Release/Radar.dll

Or from command line:
```
"C:\Program Files\Microsoft Visual Studio\2022\Community\MSBuild\Current\Bin\MSBuild.exe" Radar.sln -p:Configuration=Release -p:Platform=x64
```

## Installing

Copy the folder (or just the built DLL) into POE2Fixer's plugin
directory:

    POE2Fixer/Plugins/Radar/Radar.dll

Restart POE2Fixer. Enable Radar in the Plugins tab.

## Source

The same source is shipped inside the main POE2Fixer repo at
`Plugins/Radar/`. This standalone repo is for plugin authors who
want to fork it as a template.

## SDK Version

This plugin targets v6 of the Plugin SDK. The bundled `sdk/` headers
must match the host POE2Fixer's expected SDK version (run-time check
will refuse mismatched plugins with a clear log entry).

## Project Structure

```
sdk/            Plugin SDK headers (PluginAbi.h, PluginSDK.h)
imgui/          ImGui library (headers + sources, compiled into the DLL)
Radar.cpp       Main plugin entry point
RadarSettings.h Settings POCO with JSON persistence
```
