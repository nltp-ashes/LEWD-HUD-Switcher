# LEWD HUD SWITCHER [![License](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

---

Utility script used to provide smooth transition between different scopes.

---

### ABOUT

S.T.A.L.K.E.R. relies on a gigantic hack to handle weapon scopes. When applying a scope on a weapon, the weapon is destroyed, and a copy of it (with the scope built-in) is given to the player.

This does not natively allow for smooth transitions, so this script takes a shot at addressing that. This script will replace the draw animation of the copy of the weapon, with a custom one (defined in ltx) to guarantee a more seamless transition.

The `lewd_hud_switcher.script` will look for specific lines in the weapon config :

- **Name**          : `lewd_hud_switcher_enabled`  
  **Presence**      : Required  
  **Default value** : N/A  
  **Description**   : Master safe, to enable/disable the script

- **Name**          : `lewd_hud_switcher_next`  
  **Presence**      : Required  
  **Default value** : N/A  
  **Description**   : Name of the section to switch to when the keybind is pressed

It will also look for specific lines in the weapon HUD config :

- **Name**          : `anm_lewd_hs_transition`  
  **Presence**      : Required  
  **Default value** : N/A  
  **Description**   : Animation configuration. Hands anim, item anim, speed

Example :

```INI
my_weapon]
scopes                          = some_scope
```
```INI
[my_weapon_some_scope]
hud                             = my_weapon_some_scope_hud
lewd_hud_switcher_enabled       = true
lewd_hud_switcher_next          = my_weapon_some_scope_off

[my_weapon_some_scope_hud]
anm_lewd_hs_transition          = my_hands, my_gun_transition_on_to_off
```
```INI
[my_weapon_some_scope_off]
hud                             = my_weapon_some_scope_off_hud
lewd_hud_switcher_enabled       = true
lewd_hud_switcher_next          = my_weapon_some_scope
                                                   
[my_weapon_some_scope_off_hud]
anm_lewd_hs_transition          = my_hands, my_gun_transition_off_to_on
```

### REQUIREMENTS

The following are **absolutely required** for the script to work :
1. [S.T.A.L.K.E.R. Anomaly 1.5.2](https://www.moddb.com/mods/stalker-anomaly/downloads/stalker-anomaly-151-to-152);
2. [DLTX and DXML](https://github.com/themrdemonized/STALKER-Anomaly-modded-exes).

---

### INSTALLATION

To **install** the addon :
1. Download and install the requirements;
2. Download this addon;
3. Merge the contents of the gamedata folder with your game's folder of the same name;
   - Either with a mod manager JSGME/MO2 (highly recommended);
   - Or manually (highly unrecommended).

To **update** the addon :
1. Delete the files from the previous version;
   - By disabling the addon in your mod manager, and then deleting the files;
   - Or by deleting the files one by one if you added them manually;
2. Add in the new files from the new version;
   - Either with a mod manager JSGME/MO2 (highly recommended);
   - Or manually (highly unrecommended).

To **uninstall** the addon :
1. Simply remove the files added by the addon.

---

### CHANGELOG

For past updates, please refer to the description of each release, in the [releases tab](https://github.com/nltp-ashes/LEWD-HUD-Switcher/releases).

---

### LICENSE

This script is licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

This means you're allowed to redistribute and/or adapt the work, as long as you respect the following criteria :
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
- **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.
