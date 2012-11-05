MSBuild-Tasks
=============

Useful MSBuild inline tasks and targets. Import the common.tasks and/or common.targets to your project file and use. 

Usage examples

Zip task:

```xml
  <Target Name="BeforeBuild">
    <ItemGroup>
      <FilesToZip Include="$(ProjectDir)\PayloadUnzipped\*.*" />
    </ItemGroup>
    <Zip 
      InputFileNames="@(FilesToZip)"
      OutputFileName="$(ProjectDir)$(TargetZipFile)"
      OverwriteExistingFile="true" />
  </Target>
```

SafeGitClean:

```
msbuild common.targets /p:BackupDir=C:\temp\backup /p:DeleteBackupDir=true
```

If BackupDir is not provided a directory in %TEMP% will be created
The default value for DeleteBackupDir is 'false' 