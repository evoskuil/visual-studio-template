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

The `$(ProjectDir)$(ProjectName).props` file is your custom file containing all unique properties for the project. Generally this is the set of includes, libraries, preprocessor statements and warning overrides.

The following combinations are achieved by referencing the desired build configuration, e.g. `DynamicDebug.props`, and platform properties, e.g. `Win32.props`, as shown above.

**Dynamic libraries linked dynamically to CRT**
```
DebugDLL|Win32
ReleaseDLL|Win32
DebugDLL|x64
ReleaseDLL|x64
```
**Static libraries linked using LTCG and statically to CRT**
```
DebugLTCG|Win32
ReleaseLTCG|Win32
DebugLTCG|x64
ReleaseLTCG|x64
```
**Static libraries linked statically to CRT**
```
DebugLIB|Win32
ReleaseLIB|Win32
DebugLIB|x64
ReleaseLIB|x64
```
**Applications linked dynamically to CRT**
```
DebugDEXE|Win32
ReleaseDEXE|Win32
DebugDEXE|x64
ReleaseDEXE|x64
```
**Applications linked using LTCG and statically to CRT**
```
DebugLEXE|Win32
ReleaseLEXE|Win32
DebugLEXE|x64
ReleaseLEXE|x64
```
**Applications linked statically to CRT**
```
DebugSEXE|Win32
ReleaseSEXE|Win32
DebugSEXE|x64
ReleaseSEXE|x64
```
