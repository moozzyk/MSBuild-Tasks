MSBuild-Tasks
=============

Useful MSBuild inline tasks. Import the common.tasks to your project file and use. 

Usage example:

  <Target Name="BeforeBuild">
    <ItemGroup>
      <FilesToZip Include="$(ProjectDir)\PayloadUnzipped\*.*" />
    </ItemGroup>
    <Zip 
      InputFileNames="@(FilesToZip)"
      OutputFileName="$(ProjectDir)$(TargetZipFile)"
      OverwriteExistingFile="true" />
  </Target>
