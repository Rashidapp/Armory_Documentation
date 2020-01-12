# Deploying to Android

Before running on mobile device, make sure the project is optimized to consume minimal resources. It is recommended to create a `Mobile` render path in `Properties - Render - Armory Render Path`. Additionally, simplifying materials, textures and geometry may be needed. To run on the lower than the maximum available resolution, set `Armory Render Path - Post Process - Resolution` property.

## HashLink (C)

Create a new preset in `Properties - Render - Armory Exporter` and select Android target. Hit `Publish` to generate android project files.

To proceed, install and run [Android Studio](https://developer.android.com/studio/index.html). Select `Open an existing Android Studio project`. The project is located at `blend_file_location/build_projectname/android-native-hl-build/projectname`.

![](https://github.com/armory3d/armory_wiki_images/raw/master/deploy/android/0.jpg)

Once the project is loaded, Android Studio will install required dependencies. Make sure to allow installing NDK. Afterwards, connect your device and press `Run`.

*Note: Armory will target gles3 by default. If you require gles2 support, enable `Legacy Shaders` option in Armory add-on preferences.*

![](https://github.com/armory3d/armory_wiki_images/raw/master/deploy/android/1.jpg)

---

By default .apk file will contain all build variants. You can specify the desired ones using `abiFilters` in `build.gradle`. Default scene using mobile render path is expected at `~1.3MB` for the .apk file targetting `arm64-v8a`.

```
android {
	buildTypes {
        release {
            ndk {
                abiFilters "arm64-v8a"
            }
        }
    }
}
```
