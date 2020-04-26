# Deploying to Linux

## Krom (JS)

- Create a new preset in `Armory Exporter` and select `Linux (Krom)` target.
- Press `Publish`.
- Press `Triangle - Open Folder` to view exported files.

## HashLink (C)

Create a new preset in `Properties - Render - Armory Exporter` and select `Linux (C)` target. Hit `Publish` to export build files.

For the C++ compilation to succeed you might need to install some additional packages - read more at [Kha/Wiki](https://github.com/Kode/Kha/wiki/Linux).

Afterwards, you can compile the project using the generated Code::Blocks project file `projectname.cbp` located at `blend_file_location/build_projectname/linux-hl-build/`. In Code::Blocks, you may choose the `Release` setting for building a binary with smaller size, though it might take a longer time to build than the default `Debug` setting.

In order for the resources to load correctly you will need to copy the executable into the folder with all the game resources. Copy the executable from `blend_file_location/build_projectname/linux-hl-build/bin/Release` into `blend_file_location/build_projectname/linux-hl`.

You can now package and distribute this folder.
