# Install Minecraft GregTech New Horizons
## Install optimized Java version
Download [OpenJDK](https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/tag/jdk8u212-b04_openj9-0.14.2) java version matching your system architecture. 
Most probably you will go for x64 Windows destribution with .msi installer. [OpenJDK8U-jdk_x64_windows_openj9_8u212b04_openj9-0.14.2.msi
](https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u212-b04_openj9-0.14.2/OpenJDK8U-jdk_x64_windows_openj9_8u212b04_openj9-0.14.2.msi)

Install it following the wizard guides leaving all settings default.

## Install Minecraft Launcher
Download [MultiMC](https://multimc.org/) launcher and unpack launcher files into directory of your choise. 
Run the MultiMC.exe, it will guide you through first time launch setup.

On Java decision step point the launcher to just installed OpenJDK version. Default path for it would be `C:\Program Files\AdoptOpenJDK\jre-8.0.212.04-openj9\bin\javaw.exe`.

Login into your Minecraft/Microsoft account by going to `Profiles` -> `Manage Accounts` -> `Add Microsoft` and following instructions. (It will ask you to follow link and input code and credentials. Loading bar is fake.)

## Install GTNH Modpack
Download the 2.2.0.0 version of [GT New Horizons (MultiMC package version)](http://downloads.gtnewhorizons.com/Multi_mc_downloads/).

In MultiMC launcher click `Add Instance` -> `Import from zip`.
Click `Browse` and select just downloaded `GT_New_Horizons_2.2.0.0_(MMC).zip`.
Click `OK`.

## Update settings for the game instance
Right click on the game instance GT_New_Horizons_2.2.0.0_(MMC) and go to `Edit instance`.
Select the `Settings` tab.

Check `Memory` checkbox and set minimum and maximum memory allocation depending on your available RAM. 

>GTNH recommends between 4GB and 6GB of RAM, use more with careful consideration and testing. Setting -Xms much lower than -Xmm can cause pauses whilst the garbage collector to try to get back down to the minimum.

>Give 6G of RAM to the modpack, or the maximum you can allocate without saturating your PC (If you have 4 or less total, it will be hardly playable at all. With 8 total, assign 5-6GB). The minimum amount of RAM given should match the maximum amount of RAM given for optimal performance, to prevent overly aggressive garbage collection behavior. Allocating more than 8GB may cause issues, since the Java Garbage Collector gets worse with larger amounts of memory. Remember the rest of your system needs some left over memory as well.

>4 GB = 4096\
>5 GB = 5120\
>6 GB = 6144\
>7 GB = 7168\
>8 GB = 8192

Check `Java arguments` checkbox and insert the following options into text area.
```
-d64
-XX:+UseG1GC
-XX:+UnlockExperimentalVMOptions
-XX:+DisableExplicitGC
-XX:MaxGCPauseMillis=80
-Dsun.rmi.dgc.server.gcInterval=2147483646
-XX:G1NewSizePercent=20
-XX:G1ReservePercent=20
```

## Launching the game
Launch the game! It will take a few minutes to launch the game (3 to 5 minutes for me), longer for the first time.

(Be warned that it plays LOUD music on main screen)

## More optimizations

Optifine can cause glitches on some systems but usually it's wrong settings if you get any glitches or crashes. So I do recommend to use this, contact me if you have any issues with it.

Download [OptiFine mod 1.7.10 HD U E7](https://optifine.net/adloadx?f=OptiFine_1.7.10_HD_U_E7.jar).
Click `View mods` -> `Add` -> Select downloaded optifine mod file (`OptiFine_1.7.10_HD_U_E7.jar`)

(Optional) Together with OptiFine loading screen with progress bar makes the game load slower. So if you prefer faster load to fancy loading screen deselect checkbox `Better Loading Screen GTNH` in mod list.

When the game is launched you will have to modify some graphics settings. Go to menu -> `Options` -> `Video settings`:
```
!!!DO NOT TOUCH Chunk Loading!!!
Render Distance: 10 is a good compromise between distance and performance, you can also try different settings here
Advanced OpenGL: Fast
Performance: 
    Smooth FPS: Try out what works best for you
    Fast Math: ON
    Fast Render: ON
    Smooth World: ON


```

Check if your PC uses the right GPU. Mine uses Integrated Graphics Card instead of Nvidia one by default which lowers performance significantly.
The GPU used can be viewed by pressing F3.

## Hate high FPS? C'mon install shaders!

In case you have a billion dollar graphics card you can install some shaders to make Minecraft look nice. Here is a [guide](https://gtnh.miraheze.org/wiki/Shaders).
You will need to have OptiFine installed and running. 

[Sildur's Shaders downloads](https://sildurs-shaders.github.io/downloads/) Feel free to install newer versions.

## Useful links
[Guide to optimizations for Low End PCs](https://gtnh.miraheze.org/wiki/Low_End_PCs) Many of them already included in this guide.
[Server setup](https://gtnh.miraheze.org/wiki/Server_Setup)
