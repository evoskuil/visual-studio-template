visual-studio-template
======================

A solution, project, props, and nuget packaging templates for typical library scenarios.

These props files can be integrated into a Visual Studio `.vcxproj` file as follows:

```
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='DebugDLL|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props"
       Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" 
       Label="LocalAppDataPlatform" />
    <Import Project="$(ProjectDir)$(ProjectName).props" />
    <Import Project="$(ProjectDir)..\properties\DynamicDebug.props" />
    <Import Project="$(ProjectDir)..\properties\Win32.props" />
  </ImportGroup>
```

The `$(ProjectDir)$(ProjectName).props` file is intended to be an independent file containing all unique properties for the project.

The following combinations are achieved by referencing the appropriate pair of properties files as shown above:

**Libraries**
```
DebugDLL|Win32
ReleaseDLL|Win32
DebugDLL|x64
ReleaseDLL|x64
DebugLTCG|Win32
ReleaseLTCG|Win32
DebugLTCG|x64
ReleaseLTCG|x64
DebugLIB|Win32
ReleaseLIB|Win32
DebugLIB|x64
ReleaseLIB|x64
```
**Applications**
```
DebugDEXE|Win32
ReleaseDEXE|Win32
DebugDEXE|x64
ReleaseDEXE|x64
DebugLEXE|Win32
ReleaseLEXE|Win32
DebugLEXE|x64
ReleaseLEXE|x64
DebugSEXE|Win32
ReleaseSEXE|Win32
DebugSEXE|x64
ReleaseSEXE|x64
```
