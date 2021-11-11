# Parachute (fixed for Plasma 5.23)

## Original project is paused. It's just a fork with fix for Plasma 2.23. Nothing else. 

<p align="center">
  <img src="parachute.svg">
</p>

Look at your windows and desktops from above.
### Usage
After activate the script in *KWin Scripts* window you can use the default registered global shortcut **Ctrl+Super+D (Ctrl+Meta+D)** to show/hide *Parachute*.

![](parachute.png)

## Installation or upgrade

  ```
  git clone https://github.com/Evv1L/Parachute.git && cd Parachute
  make install
  ```
 This fork have custom version for script - v0.9.1.1
 ### Errors
If you have installed Parachute before and get "File exists" or "MakeFile Error 1" delete this file:
```
rm ~/.local/share/kservices5/Parachute.desk
```

If you have installed through Plasma's Get Hot New Stuff ([Kde Store](https://store.kde.org/p/1370195/)) you must execute the following commands on terminal to install the configuration dialog. You only need to do this once.

  ```
  mkdir -p ~/.local/share/kservices5
  ln -s ~/.local/share/kwin/scripts/Parachute/metadata.desktop ~/.local/share/kservices5/Parachute.desktop
  ```

### Uninstall
To uninstall, first go to the folder where you cloned Parachute, then run:

  ```
  make uninstall
  ```

## Run Parachute with Meta key
```
kwriteconfig5 --file ~/.config/kwinrc --group ModifierOnlyShortcuts --key Meta "org.kde.kglobalaccel,/component/kwin,org.kde.kglobalaccel.Component,invokeShortcut,Parachute"
qdbus org.kde.KWin /KWin reconfigure
```
If it doesn't work try to restart KWin with `kwin_x11 --replace`


<br>
<br>

## Controls:
* Left mouse button - Activate window.
* Middle mouse button - Close window.
* Right mouse button - (Un)pin window.
* Arrow keys - Select a window.
* Shift + Arrow keys - Switch desktops.
* Home/End - Select first/last window.
* Enter - Activate selected window.
* Esc - Hide Parachute.
* F5 - Update settings.

## Notes

* Developed and tested in *Plasma* >= 5.20 and *Qt* >= 5.15.
* For now it doesn't work on *Wayland*.
* You can use *KWin's* global shortcuts normally while using this script. To navigate between your desktops for example.
* If you are using "Slide" animation to switch desktops, you may want to enable the "Slide docks" option to avoid some [unwanted visual effects](https://github.com/tcorreabr/Parachute/issues/1).
* If you are having poor performance on animations, try changing "Scale method" to "Smooth" or "Crisp" in Compositor settings.
* If you have [Virtual Desktop Bar](https://github.com/wsdfhjxc/virtual-desktop-bar) installed, [Parachute keyboard shortcut may be ineffective](https://github.com/tcorreabr/Parachute/issues/14) until KWin restart or dynamic desktop operations.
