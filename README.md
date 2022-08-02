### Pretty Starship Config

[starship.rs](https://starship.rs/) is a cross-shell prompt which allows you to configure the appearance of a lot of common shells through config settings in a TOML file. 

I've based mine on [@TarunDaCoder's](https://github.com/TarunDaCoder) [script](http://ix.io/3Wck) and other bits and bobs I found online (I'd recommend exploring starships' discord for inspo!). I'll also include below the steps I followed to install and use starship in Windows cmd as I struggled to do so on my own.

![image](https://user-images.githubusercontent.com/62070358/182375614-02a9feff-a7b8-4e68-adae-b132f5f78f6e.png)


#### Installation Guide
##### I worked on this over a few days so I might have skipped some critical steps, please raise an issue / comment if you spot something!

1. Install [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-gb&gl=GB). I was using cmd.exe but unfortunately it does not render Unicode emojis correctly. You can run cmd from Windows Terminal.
2. Download a [Nerd Font](https://www.nerdfonts.com/font-downloads). I went for DejaVuSansMono. Unzip and install the font.
3. Activate the font in Windows Terminal (left click > settings > Profiles (Command Prompt) > Additional Settings (Apearance) > Select the font you have just installed
4. At this point you should restart your computer to ensure changes have been made
5. [Install clink](https://github.com/chrisant996/clink/releases) either through the .zip or .exe 
6. Install starship through scoop or other package managers as listed [here](https://starship.rs/guide/#%F0%9F%9A%80-installation) or [through .msi or .zip files](https://github.com/starship/starship/releases/tag/v1.9.1)
7. Create starship.lua as a new file at this path: AppData\Local\clink (if you can't find AppData folder, it might be hidden -> Inside File Exporer top ribbon > View > Show > toggle Hidden Items)
8. Insert this into the starship.lua file 

```lua
load(io.popen('starship init cmd'):read("*a"))()
os.setenv('STARSHIP_CONFIG', 'C:\\Users\\[YOURUSER]\\AppData\\Local\\clink\\.config\\starship.toml')
```

9. Find the starship.toml file in AppData\Local\clink\.config and copy in my .toml script or create your own! Happy starshipping 🚀

Notes: my .lua file has a commented-out moduled called custom.emoji. I haven't had time to implement it but you can find the instructions to activate it [here](https://starship.rs/config/#custom-commands)
