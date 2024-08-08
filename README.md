 ![screenshot](screenshot.png) 
 
![screenshot2](screenshot2.png) 
 
mostly a waybar update, just install stuff from arch-dots repo to get this working. 
also, lockscreen rofi widget needs inetutils package on arch to show the hostname. 
font is Mono Nerd Font. 
wallpapers are now controlled through [waypaper](https://github.com/anufrievroman/waypaper) 
 
note when porting over rofi modules you can't just copy paste the folder you need to re-install the rofi modules by following the directions on the [repo](https://github.com/adi1090x/rofi)  
  
also no longer using wofi, using the rofi [wayland fork](https://aur.archlinux.org/packages/rofi-lbonn-wayland) 
 
future plans: making a tool which updates accent color system-wide using the waypaper [post command](https://anufrievroman.gitbook.io/waypaper/configuration) and this script to get the current wallpaper:  
ps aux |grep swaybg |awk -F ' ' '{print $13;exit;}' 
 
probably need to find a tool (maybe imagemagick?) which extracts color pallete from an image, so the flow would probably be something like this: 
1. changing the wallpaper in waypaper triggers the post_command, in it we execute a script which: 
2. pipes the current wallpaper to the color pallete extractor. 
3. pipes the color pallete to a script which overwrites the color in the hyprland, waybar, and rofi config files. 
4. profit.

Operating system: [Arch Linux](https://archlinux.org/)  
Window manager: [Hyprland](https://github.com/hyprwm/Hyprland)  
Launcher: [Rofi](https://github.com/davatorium/rofi)  
System bar: [Waybar](https://github.com/Alexays/Waybar)  
Terminal: [foot](https://codeberg.org/dnkl/foot)  
GTK3 settings: [nwg-look](https://github.com/nwg-piotr/nwg-look)  
Rofi modules: [adi1090x/rofi](https://github.com/adi1090x/rofi)  
Screenshots: [grim](https://sr.ht/~emersion/grim/)  
Notifications: [dunst](https://github.com/dunst-project/dunst)  
Wallpapers: [swaybg](https://github.com/swaywm/swaybg)  

#### [Custom script for setting wallpaper in Thunar]  
`echo %f > /home/shahwaiz/wallpaper && swaybg -i %f -m fill`
