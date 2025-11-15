# Memory Allocation Guide for Minecraft Modpacks

This guide explains how to allocate more RAM to Minecraft modpacks on both **Modrinth** and **TLauncher** launchers. Allocating more RAM can significantly improve performance, reduce lag, and prevent crashes when running modpacks.

## Table of Contents
- [Why Allocate More RAM?](#why-allocate-more-ram)
- [How Much RAM Should I Allocate?](#how-much-ram-should-i-allocate)
- [Modrinth Launcher](#modrinth-launcher)
- [TLauncher](#tlauncher)
- [Troubleshooting](#troubleshooting)

---

## Why Allocate More RAM?

Minecraft modpacks, especially larger ones, require more memory than vanilla Minecraft. Without enough RAM:
- The game may crash frequently
- You may experience stuttering and low FPS
- Chunk loading can be slow
- Server/world loading may take longer

---

## How Much RAM Should I Allocate?

The amount of RAM you should allocate depends on the modpack size and your system's total RAM:

| Modpack Size | Recommended RAM | Your System RAM Required |
|--------------|----------------|--------------------------|
| Light (< 50 mods) | 3-4 GB | At least 8 GB |
| Medium (50-100 mods) | 4-6 GB | At least 8 GB |
| Heavy (100-200 mods) | 6-8 GB | At least 12 GB |
| Very Heavy (200+ mods) | 8-12 GB | At least 16 GB |

**Important:** Never allocate all your system RAM to Minecraft! Leave at least 2-4 GB for your operating system and other applications.

---

## Modrinth Launcher

### Step-by-Step Instructions:

1. **Open Modrinth Launcher**
   - Launch the Modrinth App on your computer

2. **Navigate to Your Profile**
   - Find the modpack you want to configure in your list of installed profiles
   - Click on the profile to select it

3. **Access Profile Settings**
   - Click the **three dots** (⋯) or **gear icon** next to your profile name
   - Select **"Edit"** or **"Profile Settings"** from the dropdown menu

4. **Find Memory Settings**
   - Look for the **"Java"** or **"Memory"** section
   - You should see options for memory allocation

5. **Adjust Memory Allocation**
   - Find the **"Maximum Memory"** or **"RAM"** slider/field
   - Set your desired amount (e.g., 4096 MB = 4 GB, 6144 MB = 6 GB, 8192 MB = 8 GB)
   - Some launchers show it in GB, others in MB (1 GB = 1024 MB)

6. **Save Settings**
   - Click **"Save"** or **"Done"** to apply your changes

7. **Launch Your Modpack**
   - Start the modpack and check if performance has improved

### Alternative Method (JVM Arguments):

If you prefer manual configuration:
1. In the profile settings, find **"JVM Arguments"** or **"Advanced Settings"**
2. Look for the argument `-Xmx` (this controls maximum memory)
3. Modify it to your desired value: `-Xmx6G` (for 6 GB) or `-Xmx8G` (for 8 GB)
4. You can also set minimum memory with `-Xms` (e.g., `-Xms4G`)

Example JVM arguments:
```
-Xms4G -Xmx6G -XX:+UnlockExperimentalVMOptions -XX:+UseG1GC
```

---

## TLauncher

### Step-by-Step Instructions:

1. **Open TLauncher**
   - Launch TLauncher on your computer

2. **Access Settings**
   - Click on the **"Settings"** button (usually a gear icon) in the bottom right or top right corner
   - Or click on the **"TL"** icon and select **"Settings"**

3. **Navigate to Java Settings**
   - In the settings menu, look for the **"Java"** tab or section
   - You may also find it under **"Advanced Settings"**

4. **Adjust Memory Allocation**
   - Find the **"RAM"** or **"Memory Allocation"** slider/dropdown
   - Select or enter your desired amount (e.g., 4096 MB, 6144 MB, 8192 MB)
   - TLauncher typically shows memory in MB:
     - 4 GB = 4096 MB
     - 6 GB = 6144 MB
     - 8 GB = 8192 MB
     - 10 GB = 10240 MB

5. **Enable the Settings**
   - Make sure the **"Use custom memory settings"** or similar checkbox is **enabled**
   - Some versions have a checkbox that says **"Allocate memory"**

6. **Save Settings**
   - Click **"Save"** or **"OK"** to apply your changes
   - The settings will apply to all profiles unless you configure them individually

7. **Launch Your Modpack**
   - Select your modpack profile from the dropdown
   - Click **"Play"** to start the game

### Profile-Specific Settings (TLauncher):

To set different RAM amounts for different modpacks:
1. Select your modpack profile from the main launcher dropdown
2. Click the **profile name** or **profile settings icon**
3. Check **"Use custom settings for this profile"**
4. Set the RAM allocation specifically for that profile
5. Save and launch

### Using JVM Arguments (Advanced):

For more control:
1. In TLauncher settings, find **"JVM Arguments"** section
2. Enable **"Use custom JVM arguments"**
3. Add or modify arguments:
   ```
   -Xms4G -Xmx8G -XX:+UseG1GC -XX:+UnlockExperimentalVMOptions -XX:G1NewSizePercent=20 -XX:G1ReservePercent=20 -XX:MaxGCPauseMillis=50 -XX:G1HeapRegionSize=32M
   ```
4. Adjust `-Xmx` value to your desired maximum RAM (e.g., `-Xmx8G` for 8 GB)
5. Save and launch

---

## Troubleshooting

### Game Won't Launch After Changing RAM:
- **Reduce the RAM allocation** - You may have allocated more than your system can handle
- **Check Java version** - Make sure you're using Java 17 or newer for Minecraft 1.17+
- **Verify available RAM** - Ensure your system has enough free RAM

### Still Experiencing Lag:
- **Update graphics drivers**
- **Close unnecessary background applications**
- **Try different JVM arguments** - Some modpacks perform better with specific optimization flags
- **Consider upgrading your hardware** if you're running very large modpacks

### "Could not reserve enough space" Error:
- This means you tried to allocate more RAM than available
- **Reduce RAM allocation** by 1-2 GB
- **Close other applications** to free up memory
- **Restart your computer** to clear memory

### How to Check Current RAM Usage:
- **In-game:** Press `F3` to see debug information (top right shows allocated/used memory)
- **Windows:** Open Task Manager (Ctrl+Shift+Esc) and check the Performance tab
- **macOS:** Open Activity Monitor and check the Memory tab
- **Linux:** Use `htop` or `free -h` command in terminal

---

## Additional Tips

1. **64-bit Java Required:** Make sure you have 64-bit Java installed to allocate more than 4 GB of RAM
2. **Regular Restarts:** Restart Minecraft every few hours during extended play sessions to clear memory leaks
3. **Optimize Settings:** Lower render distance and graphics settings if you're still experiencing issues
4. **Update Mods:** Keep your modpack and mods updated for better performance and bug fixes
5. **SSD Recommended:** Installing Minecraft on an SSD can significantly improve loading times

---

## Contributing

If you have suggestions or improvements for this guide, please feel free to contribute!

---

## License

This guide is provided as-is for educational purposes. Feel free to share and modify as needed.
