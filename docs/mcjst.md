# Minecraft Java Server on Termux <Badge type="info" text="Alpha 1.0" />
 ::: warning Read this first
This Script is still in beta stage. You may customize the "..._version.sh" to add your jars.
:::
 Minecraft Java Server on Termux. Or MJSoT is A Simple Script for Installing Minecraft Server on Termux

## Installation
 Im assuming you have already installed git. If you don't, Enter these command
 ``` bash
 pkg install git -y
 ```
 Installed? now run these command
 ``` bash
 git clone https://github.com/ImadeRamadany09/MCJavaServerTermux.git && chmod +x MCJavaServerTermux && cd MCJavaServerTermux && ./setup.sh
 ```
 Follow the installation then You will be done

## How does it work?
### Whats what
 The script : setup.sh
 The directory : Mineraft_Server in Your Internal storage (/sdcard)
 ### This is How it Works
 First, The script will do an upgrade pkg's in termux, then it will download its depedencies (Which is available in termux repository).
 After that, The script will make a directory in Phone Internal Storage and made a link to the termux so the directory is connected between Internal Storage and termux.
 Why did this? Did this for easier server managing.
 Then, in the directory, The script will give Options
 ```
 1. Vanilla
 2. Paper
 3. Spigot
 ```
 Choosing any of these Option will give you another option based on the first option you picked
 For example. Selecting Vanilla Option (1) Will give You another option which version you'll install
 like
 ```
 1.16.5
 1.17.1
 ```
 You can add another version by modifying a file named vanilla_versions.sh or paper_versions.sh if you selected Paper Option (2)
 Look at the structure
 ```
 declare -A MINECRAFT_VERSIONS
 MINECRAFT_VERSIONS=(
    ["1.17.1"]="https://piston-data.mojang.com/v1/objects/a16d67e5807f57fc4e550299cf20226194497dc2/server.jar"
    ["1.17"]="https://piston-data.mojang.com/v1/objects/0a269b5f2c5b93b1712d0f5dc43b6182b9ab254e/server.jar"
 )
 ```
 You can add another version by making a new line under ["1.17"] Variable
 Example
 ```
 declare -A MINECRAFT_VERSIONS
 MINECRAFT_VERSIONS=(
    ["1.17.1"]="https://piston-data.mojang.com/v1/objects/a16d67e5807f57fc4e550299cf20226194497dc2/server.jar"
    ["1.17"]="https://piston-data.mojang.com/v1/objects/0a269b5f2c5b93b1712d0f5dc43b6182b9ab254e/server.jar"
    ["1.21.1"]="https://piston-data.mojang.com/v1/objects/a16d67e5807f57fc4e550299cf20226194497dc2/server.jar"
 )
 ```
 After choosing. Then it will download the server.jar in The directory. When done, It will Make a Question if you agree to Mojang Eula. if You dont, then you need to make it Yourself.
 When done, It will generate JVM args (Need to enter your RAM Size) and save it to start.sh . To start it. Open Termux(If You don't already) and enter The directory then start by entering this command to termux
 ``` bash
 ./start.sh
 ```
 
