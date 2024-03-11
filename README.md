# BuildOutputProblem

This solution is intended to showcase an issue that occurs with Visual Studio 2022 v17.9.  This behavior does not occur with older versions.

- Open the solution file BuildOutputProblem.sln
- Choose Build > Rebuild Solution
- Open File explorer and inspect the folder at:  $(SolutionDirectory)\bin and bin\plugins.
- At this point everything is correct.  The bin folder should have WpfApp.exe and SharedLibrary.dll.  The plugins folder should have PluginLibrary.dll
- R-click on the plugin project and choose Rebuild Project.   Still the build output doesn't change.
- Now from the main menu choose Build > Build Solution (not rebuild, normal build).   Now you will see that SharedLibrary.dll shows up in the plugins folder.  That is the defect. It behaves like it is ignoring the UseCommonOutputDir setting in the CSPROJ file.

