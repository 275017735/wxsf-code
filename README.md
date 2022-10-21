# wxsf-code
wxShapeFramework for wxWidgets by Michal Bližňák


I was able to build wxSF and the demo app with VS2017 and wxWidgets 3.2.0.

- download wxWidgets 3.2.0 sources and extract
- open <wxdir>/build/msw/wx_vc15.sln (Use the one that matches your VS version)
- build the configurations "DLL Debug" and "DLL release"
- set WXWIN environment variable to the root of your wxWidgets directory
- relog Windows (needed for the environment variable to be set)

Now to wxSF
- use create_build_files.bat to create build files for VS 2005/2008
- use default option 2
- open the created solution file in VS

The wxSF solution files expect a monolithic build of wx2.8, so some changes to the configuration are needed:

Open solution properties and go to Linker -> Input -> Additional Dependencies
Replace wxmsw28ud.lib with:
wxmsw32ud_core.lib
wxbase32ud.lib
wxbase32ud_xml.lib

Build wxSF
There are lots of warnings about a deprecated function, but you can ignore those.

Switch to wxSFDemo project.

Again, open solution properties and go to Linker -> Input -> Additional Dependencies
and make the same changes as above.

Build wxSFDemo

These steps worked for me.
