## DEMO-AddAudioKit

### *Tech Used*
* Xcode 9.3+
* Swift 4.0+
* iOS 11.3+
* AudioKit 4.2.2

Frameworks:  
- UIKit
- AudioKit

### *Description*

This app demonstrates a simple use of the [AudioKit](https://audiokitpro.com) framework for manipulating sound and music - once you've added the required AudioKit frameworks (AudioKit and AudioKitUI) per the instructions below. (This project has been tested with AudioKit-iOS v4.2.2.)

To learn more about AudioKit and retrieve the pre-compiled framework binaries, full source, example playgrounds, etc, check out their [developer documentation page](http://audiokit.io).


### *Setup Requirements*

The AudioKit framework files are not included with this demo, as it is intended to be part of a tutorial for developers to learn how to add the framework files to a project.

To try this out, clone this app, then download the AudioKit-iOS zip file from the [AudioKit downloads page](http://audiokit.io/downloads/) and add it to the app using the instructions below.

Instructions for the process of adding AudioKit to the app can be found:

- on my [Medium feed (video link and text)](https://medium.com/@leannemlis/how-to-integrate-audiokit-into-an-ios-project-31e6c7c1c04a)

- on YouTube:
[![AudioKit iOS Setup](https://i.ytimg.com/vi/iUvWxWvRvo8/1.jpg)](https://youtu.be/iUvWxWvRvo8 "AudioKit iOS Setup")

- or, here, in text, step by step:

1. Get the framework:

- [Download the framework.](http://audiokit.io/downloads/) I use the [AudioKit-iOS-4.2.2.zip](http://github.com/audiokit/AudioKit/releases/download/v4.2.2/AudioKit-iOS-4.2.2.zip) in the video. The .zip files contain the pre-compiled binaries for the respective OS, along with license and other files you might be interested in checking out. You can get the full source instead, if you’d like. The full source contains a shell script to compile all the binaries. Once you’ve compiled and have the framework folders available, continue with the following instructions. (You won’t need to unzip those, of course!)

- Unzip the download, if macOS hasn’t done that for you automatically. The .zip file contains a single folder, named appropriately AudioKit-iOS or the equivalent for whichever OS you download.

2. Add the framework to your bundle:

- Copy the AudioKit-iOS folder into your project’s bundle folder. (That would be the one with all of your project’s base files (not the folder with the.xcodeproj in it).  
  Note: you actually only need the .framework subfolders within that folder. You can copy those .framework folders directly into the bundle folder — or, you can copy the entire AudioKit-... folder into the bundle folder, if you prefer a subfolder for organization. Either way, the other files (license, README, etc) are not needed for functionality; however, I leave them in the folder. As of this writing, AudioKit is offered on a MIT license, meaning that all copyright and license notices must be preserved; then, you may use the frameworks in any way you choose.

3. Update your project settings to include AudioKit:

- Click on the project name in the navigator pane to display your project settings window.

- Make sure the target is selected (not the project), in the project/target dropdown in the upper left of the editor window.

- Click on the ‘Build Phases’ tab in the editor window’s tab bar.

- Click on ‘Link Binary with Libraries’ in the Build Phases window to open that section.

- Drag the .framework folders from the bundle folder in Finder to the ‘Link Binary with Libraries’ area. Note: this doesn’t move the folders; instead it adds those folders to Xcode’s link list. You’ll also now see them in the navigator under ‘Frameworks’.

- Click on the ‘Build Settings’ tab in the editor window’s tab bar.

- Enter ‘framework search’ (without the quotes) in the search bar in the editor window’s upper right corner. As you type, Xcode will search for that phrase in the build settings. You will eventually see a setting called ‘Framework Search Paths’.  
  At this point, ensure that the search path value matches the correct location for the .framework folders OR that the path is empty if you placed the .framework folders directly into the bundle folder, rather than in a subfolder in the bundle folder.
  
- Back in the search bar, enter ‘Other Linker’. You’ll eventually see a setting called ‘Other Linker Flags’.

- Click to the right of ‘Other Linker Flags’ to edit the value for this setting.

- Add the value -lstdc++ This tells Xcode to link with the standard C++ library, which AudioKit requires.

4. Build the project!
