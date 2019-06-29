# Deploying to iOS

Before running on mobile device, make sure the project is optimized to consume minimal resources. It is recommended to create a `Mobile` render path in `Properties - Render - Armory Render Path`. Additionally, simplifying materials, textures and geometry may be needed. To run on the lower than the maximum available resolution, set `Armory Render Path - Post Process - Resolution` property.

## HashLink (C)

Create a new preset in `Properties - Render - Armory Exporter` and select iOS (C) target. Hit `Publish` to generate iOS project files.

To proceed, install [XCode](https://developer.apple.com/xcode/). Launch XCode by opening the generated project located at `blend_file_location/build_projectname/ios-hl-build/projectname.xcodeproj`. Connect your iOS device and press `Run`.

*Note: Armory will target gles3 by default. If you require gles2 support, enable `Legacy Shaders` option in Armory add-on preferences.* 
