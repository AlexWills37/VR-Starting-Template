# VR-Starting-Template
Template project for a Quest 2 VR game built in Unity.

**What's included in this project?**

This project is a template for making VR projects for the **Quest 2** in **Unity**.

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

### Building to the headset
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



