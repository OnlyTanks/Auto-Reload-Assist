# Auto Reload
# [**Showcase**](https://youtu.be/M_6caSyQQOY)

Automatically reloads the weapon you are currently holding when it is completely empty.

Auto Reload supports normal magazine weapons, round-fed weapons, and heat/heatsink weapons. It uses Helldivers 2's normal reload action, so reload animations, timings, movement restrictions, sounds, and weapon-specific behavior are still handled by the game.

## Features

- Automatically reloads your currently equipped weapon when it is truly empty.
- Counts both the magazine and any round still loaded in the chamber.
- Supports heat-based weapons and automatically replaces the heatsink after a full overheat.
- Supports primary, secondary, and support weapons.
- Optional manual reload key, defaulting to **R**.
- Manual reload key can be changed without restarting the game.
- Does not add ammo or change magazine capacity.
- Does not change heat values.
- Does not modify your existing Helldivers 2 keybinds.
- Only logs critical errors.

## Supported Weapons

Auto Reload supports most-all weapon ammo systems used by Helldivers 2:

### Magazine-fed weapons

- Primary weapons
- Secondary weapons
- Support weapons
- Machine guns and similar weapons

### Round-fed weapons

- Weapons that use individually tracked rounds or alternate round feeds

### Heat / heatsink weapons

- Laser and energy weapons that use replaceable heatsinks
- Reloads only after the weapon has fully overheated and a spare heatsink is available

### Vehicle Weapons

- Maelstrom Main Cannon
- Bastion Tank Main Cannon
- FRV HMG

The mod watches the weapon you are currently holding.

For normal weapons, it waits until:

`Magazine / loaded rounds + chambered round = 0`

For heat weapons, it waits until the weapon is fully overheated.

If no spare magazine, rounds, or heatsink is available, Auto Reload will not trigger. Since obviously theres no ammo in the weapon.

## Reload Behavior

Auto Reload uses Helldivers 2's normal/native reload action.

This means the game still controls things such as:

- Reload animation
- Reload duration
- Movement restrictions
- Weapon stance
- Chambering
- Sounds
- Weapon-specific reload behavior

The mod only decides **when to request a reload**.

It does not directly refill ammunition.

## Requirements

Requires:

[**Bingus Shared Loader v15 or newer / API 1**](https://github.com/CowboyBingus/BingusSharedLoader)

[**Mod Options Menu**](https://github.com/CowboyBingus/ModOptionsMenu)

After loading successfully, the Bingus Shared Loader log should contain:

`mods/OnlyTanks/auto_reload: loaded`

## Installation

Install **Auto Reload** together with Bingus Shared Loader using your Helldivers 2 mod manager/ HD2Arsenal.

No additional setup is required for automatic reload.

## Manual Reload Key

The optional manual reload key defaults to:

**R**

This does not replace or modify your Helldivers 2 controls. Auto Reload simply listens for the configured key and asks the game to perform its normal reload action.

The configuration file is automatically created at:

`%LOCALAPPDATA%\CowboyBingus\Helldivers2\Config\auto_reload.cfg`

Default configuration:

```ini
reload_key=R
```

You can edit the file while the game is running. The new key will be picked up automatically.

## Supported Keybinds

### Letters

`A` through `Z`

### Numbers

`0` through `9`

### Function keys

`F1` through `F12`

### Mouse buttons

`MOUSE1`  
`MOUSE2`  
`MOUSE3`  
`MOUSE4`  
`MOUSE5`

### Numpad

`NUM0` through `NUM9`

### Other supported keys

`SPACE`  
`TAB`  
`ENTER`  
`RETURN`  
`ESC`  
`ESCAPE`  
`BACKSPACE`  
`SHIFT`  
`CTRL`  
`CONTROL`  
`ALT`  
`CAPSLOCK`  
`INSERT`  
`DELETE`  
`HOME`  
`END`  
`PAGEUP`  
`PAGEDOWN`  
`LEFT`  
`RIGHT`  
`UP`  
`DOWN`

For example:

```ini
reload_key=MOUSE4
```

or:

```ini
reload_key=F6
```

## Disable the Manual Key

Automatic reload does not require a keybind.

If you only want automatic reload and do not want Auto Reload to listen for a manual reload key, use:

```ini
reload_key=NONE
```

The following also work:

```ini
reload_key=OFF
```

```ini
reload_key=DISABLED
```

## Logging

Auto Reload stays quiet during normal gameplay.

It does not create ammo tracking, reload status, or debug logs.

A log is only created if the mod encounters a critical problem:

`%LOCALAPPDATA%\CowboyBingus\Helldivers2\Logs\AutoReload.log`

If the mod stops working after a Helldivers 2 update, check this file first.

## Configuration Location

Config:

`%LOCALAPPDATA%\CowboyBingus\Helldivers2\Config\auto_reload.cfg`

Critical error log:

`%LOCALAPPDATA%\CowboyBingus\Helldivers2\Logs\AutoReload.log`

## Notes

- Automatic reload works without pressing any key.
- A chambered round is counted before automatic reload triggers.
- Heat weapons only reload after a full overheat.
- The game still decides whether the weapon is currently allowed to reload.
- Auto Reload does not give extra ammunition.
- Auto Reload does not change magazine sizes.
- Auto Reload does not change heatsink or heat values.
- Major Helldivers 2 updates may require an updated version of the mod.
