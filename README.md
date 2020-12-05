<img src="https://repository-images.githubusercontent.com/282035636/2f414480-2e50-11eb-838b-ef0822e416bb" width="200px" align="right">
<div align="center">

#
### The highly customizable, organized, and optimized checks configuration for [Anticheat](https://www.mc-market.org/resources/13999), a powerful, modern, and lightweight anticheat for Minecraft 1.8 and higher.
<br/>
</div>

<table align="center">
<tr>
<td>

**Make sure to use files compatible with your anticheat version!**  
<sub>
  Sometimes Matrix Premium updates faster than Free; there will be a directory if so.  
  Legacy releases compatible with older versions of Matrix have their own branches.
</sub>

[![Anticheat](https://img.shields.io/badge/Plugin-Matrix%20Anticheat-%237009ac?style=flat-square)](https://www.mc-market.org/resources/13999) ![Commits since release](https://img.shields.io/github/commits-since/Encode42/MatrixChecks/latest/main?label=Commits%20since%20release&style=flat-square)  
[![Checks Support](https://img.shields.io/discord/707330384328654869?color=7289DA&label=Checks%20Support&style=flat-square)](https://discord.gg/rjSkFyj) [![Matrix Support](https://img.shields.io/discord/392904793758367745?color=7289DA&label=Matrix%20Support&style=flat-square)](https://discord.gg/rGhYma6)
</td>
<td>

#### Features
- Works on free & premium Matrix.
- Tons of customization.
- Improved violation & kick messages.
- Lower amount of false positives.
- Stricter checks. *(Faster detection)*
- Multiple file types to suit your needs.
</td>
</tr>
</table>

⚠ **REQUIRED INSTALLATION NOTE:**  
You **must** install [`language.yml`](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/language.yml) to use placeholders!  
Otherwise, many messages will be unreadable! Every message  
contains placeholders that require the language file.

⚠ **GENERAL NOTE:**  
`config.yml` and `language.yml` **do not** include any checks!  
Install [`checks.yml`](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/checks.yml) to utilize the main detection changes.

## 🔧 Setup
### Server Usage
1. Download [checks.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/checks.yml) and [language.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/language.yml).  
<sub>For specific Matrix versions, head to the [releases page](https://github.com/Encode42/MatrixChecks/releases).</sub>
2. Rename Matrix's original `checks.yml` and `language.yml` to something else. `checks.old.yml`/`language.old.yml` will work.
3. Upload/move the new files to your Matrix plugin folder. (`/plugins/Matrix/`)
4. If you downloaded a file besides `checks.yml` or `language.yml`, rename the file to `checks.yml`/`language.yml`.
5. Run `/matrix reload`!

Alternatively, you can just run `/matrix dlcfg POWZQTPWMD` in-game  
to download the latest stable build of MatrixChecks. (This ID changes!)  
The downside is that all comments are removed and the file size is reduced.

### Cloud Usage
1. Download [config.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/config.yml) and [language.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/language.yml).  
2. Rename Matrix's original `config.yml` and `language.yml` to something else. `config.old.yml`/`language.old.yml` will work.
3. Change `cloud_config.enable: false` to `true` in `config.yml`.
4. Run `/matrix reload`! The checks will now update on every reboot/reload.  
<sub>For specific Matrix versions, replace `main` in the link with the compatible checks branch.</sub>

## ❔ FAQ
These checks may not work perfectly with your server.  
Plugins, software, and performance can all affect how well these checks and the anticheat, in general, will work.  
**This is not a drag-and-drop solution!** Some values may need to be changed to work best with your setup.

Matrix Anticheat, like most, isn't a perfect anticheat. It itself has bugs that we cannot fix.  
These checks aim to mitigate those issues and improve what works well, but there's only so much we can do.  
Tested and configured for survival and minigame servers. Tweak the checks for your own server!

### 1. Checks file types
#### checks.yml
The main checks file. Includes all of the advertised features.  
Conditional commands, optimized checks, increased speed, etc.

#### language.yml
The main language file. This file must be installed on every Matrix instance.  
It contains all of the global placeholders used in `checks.yml`.

#### config.yml
An optional file that only changes a few things from the original config.  
Includes organization, minor tweaks, and a pre-set cloud config for MatrixChecks.

#### /optional/kickless.checks.yml
Same as `checks.yml` but with all kick commands removed.  
This is helpful for debugging or modifying checks without getting kicked.

#### /optional/unknown.language.yml
Same as `language.yml` but with different kick messages based on confusion.  
All kick messages are replaced with a generic message and a number for staff.  
This allows staff to know why a player was kicked without letting the player knowing which hacks to disable.

#### /optional/error.language.yml
Same as `language.yml` but with different kick messages based on confusion.  
All kick messages are replaced with existing and made-up error messages.
This confuses hackers since they have no idea what they were kicked for.

#### /cloud/*
The same as the files above, but minified. These are a lot smaller in file size but are nearly impossible to read.  
Because of the small file sizes, the files can be automatically updated quickly on server startup.  
These are optimized for cloud usage with `config.yml`. For instructions, read [Cloud Usage](https://github.com/Encode42/MatrixChecks#cloud-usage).

### 2. Suggested changes
1. `autoclicker.max_cps: 18` → `16 - 24`: The highest human CPS is 24.
2. `hitbox.max-reach: 3.2` → `3.3`: If you have issues with the hitbox check.
3. `speed.tolerance: 0.0225` → `0.015 - 0.0325`: Decrease if players are bypass speed checks.
4. `fly.setback_to_void: true` → `false`: For sky-based servers when players are being teleported to the void.
5. `nofall.damage: true` → `false`: For servers with fall-damage disabled.
6. `inventory.cancel_vl: 8` → `8 - 12`: Laggy connections can cause issues with low numbers.
7. `delay.min_delay: 7` → `5 - 9`: Decrease if there are bypasses.
8. `fastplace.max_place_per_second: 16` → `9 - 19`: Decrease if there are bypasses.

### 3. How do I report a change or false positive?
**FIRST:**  
Make sure this isn't an issue with the anticheat itself. Test with the [default Matrix config files](https://github.com/jiangdashao/Matrix-Issues) to see if it's an issue with MatrixChecks. If the issue persists, it's most likely an issue with Matrix. Not all issues can be fixed with a checks file tweak. Head over to [Matrix's support Discord](https://discord.gg/wjheaRj) and ask about the issue, or report the issue at their [issue tracker](https://github.com/jiangdashao/Matrix-Issues/issues).  
- Matrix's Discord: [Here](https://discord.gg/wjheaRj)  
- Issue tracker: [Here](https://github.com/jiangdashao/Matrix-Issues/issues)

**THEN:**  
Make an issue at the [issue page](https://github.com/Encode42/MatrixChecks/issues) with the right template. If you describe what you want to be changed/fixed thoroughly, the chances are that it'll be taken care of quickly. If you already know what the issue is or how to fix it, feel free to make a [pull request](https://github.com/Encode42/MatrixChecks/pulls) containing the change and why you made it.  
- Issue Page: [Here](https://github.com/Encode42/MatrixChecks/issues)  
- Pull Requests: [Here](https://github.com/Encode42/MatrixChecks/pulls)

### 4. There are weird things in my kick messages!
Do the "weird things" look like "`%gp_o_pr%`"? If so, you have not installed `language.yml`.  
This file is required to replace those placeholders with what they're meant to be. [Installation](https://github.com/Encode42/MatrixChecks#server-usage)

### 5. Can I modify the files in MatrixChecks?
Yes! I encourage you to do so. Since all servers are different, you most likely will have to modify the files anyway.  
You can also distribute it all you want or use it on a large network; just please don't claim it all as your own. (Credit the original authors)
