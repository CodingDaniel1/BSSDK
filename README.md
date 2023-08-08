# BSSDK
This is the unofficial Banana Shooter SDK for creating custom models.

~~To make sure your custom models will be loaded correctly you will have to make sure your .unity3d files name are source.unity3d, otherwise the game wont load it, also you have to create a config.json along with it, the config.json should look like this~~

This revision of the Banana Shooter SDK can produce multiple assets at the same time. Put as many prefabs as you want in the AssetBundles/Source directory. Make sure the prefabs render in a unity universal render pipeline project (URP).


The Program will now produce folders for each prefab as well as, the source.unity3d for the prefab, a preview png image, and a config.json.

# Modification Ideology 
## Multiple Prefabs
All folders in the AssetBundles Directory are packed into separate unity3d files, The source folder is named as such because Banana Shooter needs a source.unity3d. To recreate this I move each prefab into directories named after the prefab, then rename each prefab to model.prefab. After this the assets are packed and put into the output folder. After each file is packed. I move each .unity3d into folders named after the pack and rename the .unity3d file. ie modelABC.unity3d -> /modelABC/source.unity3d.
## Config Creation
In the previous steps in the portion of the script that moves the .unity3d(s) the file name is also used to create the config.json file in the following format
### Config Format
```json
{
  "name" : "your models name or whatever you want to show in the game"
}
```
## Image Generation
To crate the preview images I used the unity Asset Preview. There is a lot of funky coding mumbo jumbo that allows the asset to be loaded and then for the preview to be rendered and saved as a texture2d then to be converted to a png, read through it if you want but im still confused on how it all works (multiple temporary files and conversion steps)


# Know Issues
## Created models are locked to the origin X,Y position
Remove these functions in this order
1. Animations
2. Constant Applied forces
3. Rigid body position locks  
## Scripts Do nothing
I haven't figured out how to fix this yet



# ChangeLog
- July 12th: init
- July 12th: Readme Headers Fixed
- July 13th: fixed Need to run twice Error
- July 13th: fixed /source directory from being created

# Installation Proccess
To install the BSSDK and use it, please refer to the [Banana Shooter Modding Docs](https://bs-docs.readthedocs.io/en/latest/index.html)
