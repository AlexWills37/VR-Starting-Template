# VR-Starting-Template
This project is a template for making VR projects for the **Quest 2** in **Unity**.

Feel free to fork or download this repository and use it as a starting place for VR projects.


**What's included in this repository?**
- Template scene where the player can move around in VR
- VR module of the Oculus Integration Package
- [Quickstart guide](#quickstart-guide)
- [Information on Oculus Integration Package](#understanding-the-oculus-integration-package)

**Resources:**
- [Unity Hub](https://unity.com/download)
- Unity version 2021.3.23f1
    - Android Build Support module
        - Android SDK & NDK Tools module
        - OpenJDK Module
- [Oculus Integration Package v50](https://developer.oculus.com/downloads/package/unity-integration/50.0)
    > This project only contains the VR module.
    > To use other modules, you will need to download and import the full Oculus Integration Package (instructions here).

# Quickstart Guide
## Overview
This guide has three sections:
1. [Installing Unity 2021.3.23](#dowloadinginstalling-unity)
2. [Opening this template project](#opening-this-project)
3. [Building to the Quest 2](#building-to-the-headset)



## Instructions
#### Dowloading/Installing Unity
> If you have installed Unity before, you may skip some steps.

1. Download the Unity Hub from [Unity's website](https://unity.com/download).
2. [Click here](https://unity.com/releases/editor/archive) to go to Unity's download archive to find older versions.
    > Since this project uses an older version of Unity, the editor cannot be dowloaded from the Hub directly.
3. Navigate to Unity 2021.3.23.
    > Click on the **Unity 2021.X** tab and scroll down
    > until you see 2021.3.23
4. Click the **Unity Hub** button to install the editor through the Unity Hub.
    > If you do not install the editor through the Unity Hub,
    > you will not have the option to also install the Android SDK/NDK Tools or the OpenJDK modules.
    
    ![Image of Unity's download page with a red circle drawn around the Unity Hub button](https://github.com/AlexWills37/VR-Starting-Template/assets/77563588/cbf0b982-0d76-4186-a323-6b9a0d0cdb21)

5. Check the boxes for:
    - Android Build Support
        - OpenJDK
        - Android SDK & NDK Tools
    > If you forget this step, as long as the editor was installed through the Unity Hub (see step 4), you can
    > add these modules by going to the
    > **Installs** section of the Unity Hub, right-clicking the install
    > for Unity 2021.3.23, and clicking **Add modules**.
    
    ![Image of the modules that should be selected to install](https://github.com/AlexWills37/VR-Starting-Template/assets/77563588/6f523d17-33b4-4917-a810-695739a38c74)

    
6. Click continue, accept the terms and agreements, and install.

#### Opening this project
1. Clone this repository to your device.
2. In the Unity Hub, click **Add** to add a project.
3. Find and select the **Quest 2 Template** folder from this repository to add it to the Unity Hub and open the project.
    > The first time you open the project will take longer than all future times you open it.
4. When the project opens for the first time, in the top menu bar, click **Edit > Project Settings...**
    
    4a. Click on **Oculus** on the side bar

    4b. If there are any items in the **Outstanding Issues** section or **Recommended Items** section, click **Fix All** and **Apply All**.

   ![Image of the Oculus section of the Project Settings with circles around the Fix All and Apply All buttons](https://github.com/AlexWills37/VR-Starting-Template/assets/77563588/b57f78da-7810-4ec4-9eaf-6c65430fb591)


#### Building to the headset
1. Enable developer mode on the headset.
    > Follow [Meta's guide here](https://developer.oculus.com/documentation/unity/unity-env-device-setup/) in case the process ever changes.
2. Connect headset to computer with USB.
3. Follow any dialogue in the headset to allow your computer access to the headset.
4. In Unity, at the top menu bar, click **File > Build Settings**.
5. Switch target platform to Android if it isn't already chosen.
6. Under **Run Device**, select the headset. If you do not see it, click **Refresh**.
    
   ![Image of the Build Settings window with the Quest device selected](https://github.com/AlexWills37/VR-Starting-Template/assets/77563588/a054778f-e457-4c71-939d-f751861e87d0)

   
    > If you still do not see the device, ensure that the headset is connected over USB.
    >
    > If it still does not appear, ensure that on the headset developer mode is enabled and you have allowed your computer access to debugging (a window in the headset should appear when you connect to your computer, asking to allow permissions).
8. Click **Build and Run**. When it is finished, it will already be running on the headset.
    > The application is now on the headset! You can open it
    > again by going to the headset's app library, and navigating
    > to the **Unknown Sources** section.
    >
    > Notes:
    >   - You can build the same application to the headset, and it will overwrite the old version.
    >   - You cannot build the same application to the headset if it was originally built using a different computer/editor. You will have to delete the old application from the headset before being able to install it with a different computer/editor.


# Understanding the Oculus Integration Package

### File Structure
In the **Assets** section of the Unity project, the Oculus Integration Package adds an `Oculus/` folder. 
This folder contains subfolders for each module, such as `VR/` (this repository only has the VR folder. To learn how to use
other modules, look at the [Other Modules](#using-other-modules) section of this README).

You can find useful prefabs ready for adding to the project in the `Oculus/VR/Prefabs/` folder (same structure for the other modules, too).

You can find some examples of how the assets work in the `Oculus/VR/Scenes/` folder.

## Important features
### Camera Rig
To make any VR project for the Quest work, you need the **OVRCameraRig**. This is a prefab in the `Oculus/VR/Prefabs/` folder that takes care of the player's cameras and tracking their head and hands.
To use it, just add it to the scene and delete the **Main Camera** that is added to scenes by default.

**In the inspector, for the `OVR Manager` component, consider switching `Tracking Origin Type` to `Floor Level`**.
This option determines how the real world relates to the virtual world.

- **Eye Level**: the camera's starting position will start where it is placed in the scene, ignoring the player's height.
- **Floor Level**: the camera's starting position will adjust so the camera's virtual height (relatively) matches the player's starting height.
> With **Floor Level** selected, the real world floor will match the virtual floor.

### Player Controller
Instead of adding the **OVRCameraRig**, you might want to add the **OVRPlayerController** from the same folder. 
This prefab has the **OVRCameraRig** built-in, and it has the additional functions of giving the player a physical collider and the ability to move around.

You can experiment with the settings of the player controller in the inspector.

### Hands!
You can add models for the hands by dragging the models under the `LeftHandAnchor` and `RightHandAnchor` in the
hierarchy of the **OVRCameraRig**.

The `Oculus/VR/Prefabs/` folder has an `OVRControllerPrefab` 
which you can add to the `Left/RightControllerAnchor` to give the player a visual of their controller in the game.
For Quest 2 controllers, select the **L Touch** and **R Touch** options in the inspector for the left and right controllers respectively.


## Using other modules
This project only contains the VR module of the package. In my experience, I have not used any other modules (besides SampleFrameworks for example scenes and assets).
They have been left out of this repository to save space for faster downloads.

To use the other modules, follow these steps:

1. Download the Oculus Integration Package v50 from [Meta's website](https://developer.oculus.com/downloads/package/unity-integration/50.0).
    > It will save as `OculusIntegration_v50.0.unitypackage`.
2. With your project open, in the toolbar click **Assets > Import Package > Custom Package**.
3. Find and select the `OculusIntegration_v50.0.unitypackage` that you downloaded.
    > A window will appear allowing you to choose what parts
    > of the package you want to import.
4. Uncheck any parts of the package you do not want, or import all.
5. Edit the `.gitignore` file inside of the project folder to include the modules your project uses
    > This step is only necessary if you are using GitHub to manage your project.
    >
    > Alternatively, if you do not want to have the Oculus Integration Package with the GitHub, you can keep it ignored with the `.gitignore`. 
    > Remember to import the package if you ever clone the repository though. 



